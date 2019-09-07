```java

import com.google.common.hash.BloomFilter;
import com.google.common.hash.Funnels;
import lombok.extern.slf4j.Slf4j;
import org.junit.Test;
import org.springframework.util.Base64Utils;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.util.zip.ZipEntry;
import java.util.zip.ZipInputStream;
import java.util.zip.ZipOutputStream;

@Slf4j
public class BloomFilterTest {

    @Test
    public void bloomFilterUserTest() throws IOException {

        String bloomFilterStr;

        try (ByteArrayOutputStream byteArrayOutputStream = new ByteArrayOutputStream();
             ZipOutputStream zipOutputStream = new ZipOutputStream(byteArrayOutputStream)) {

            // 初始化一个可以装10000个Integer类型的布隆过滤器
            BloomFilter<Integer> filter = BloomFilter.create(Funnels.integerFunnel(), 5000);

            //导入数据到filter
            for (int i = 0; i < 10; i++) {
                filter.put(i);
            }

            // 写入到output流
            zipOutputStream.putNextEntry(new ZipEntry("bloom_filter_code"));
            filter.writeTo(zipOutputStream);
            zipOutputStream.closeEntry();

            zipOutputStream.flush();

            log.debug("字节流长度: {}", byteArrayOutputStream.toByteArray().length);

            // 这个时候byteArrayOutputStream应该包含了压缩后的bloom filter的字节流，将它转化为可打印字符
            bloomFilterStr = Base64Utils.encodeToString(byteArrayOutputStream.toByteArray());

            log.debug(bloomFilterStr);
            log.debug("字符长度: {}", bloomFilterStr.length());

            //测试验证
            for (int i = 0; i < 10; i++) {
                log.debug("i = " + i + " " + filter.mightContain(i));
            }
        }

        // 将字符串还原为bloom filter
        try (ByteArrayInputStream byteArrayInputStream = new ByteArrayInputStream(Base64Utils.decodeFromString(bloomFilterStr));
             ZipInputStream zipInputStream = new ZipInputStream(byteArrayInputStream)) {
            zipInputStream.getNextEntry();

            BloomFilter<Integer> filter = BloomFilter.readFrom(zipInputStream, Funnels.integerFunnel());

            //测试验证
            for (int i = 0; i < 10; i++) {
                log.debug("i = " + i + " " + filter.mightContain(i));
            }
        }
    }
}

```
