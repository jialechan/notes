# 目录
<b><a name="api列表" id="api列表" >API列表</a></b>

* <a href="#添加渠道">添加渠道</a>
* <a href="#获取渠道">获取渠道</a>
* <a href="#添加sdk插件">添加sdk插件</a>
* <a href="#修改sdk插件">修改sdk插件</a>
* <a href="#获取sdk插件列表">获取sdk插件列表</a>
* <a href="#添加sdk配置">添加sdk配置</a>
* <a href="#删除sdk配置">删除sdk配置</a>
* <a href="#检查插件">检查插件</a>

<b><a href="#错误码定义" >错误码定义</a></b>


# 接口列表详情
## <a name="添加渠道" id="添加渠道" >[ 添加渠道 ]</a>
### 接口说明
```txt
添加渠道
```
### 定义
```shell
curl -X POST  -d '{
	"name":"name"
}' "http://host:port/addChannel"
```

### 请求参数说明
<table>
<tr>
    <th width="100px">参数名</th><th width="100px">必要参数</th><th width="200px">限制</th><th>说明</th>
</tr>
<tr><td>name</td><td>必须</td><td>长度边界[1 : 200]<br/></td><td>渠道名称</td></tr>
</table>

### 正确返回
```json
{
	"code":0
}
```
### 正确返回参数说明
<table>
<tr>
    <th width="100px">参数名</th><th width="100px">必要参数</th><th width="200px">限制</th><th>说明</th>
</tr>
<tr><td>code</td><td>必须</td><td> --- </td><td>状态码, 0：完成</td></tr>
</table>

<a href="#api列表" style="font-size:8px;">返回api列表</a>


## <a name="获取渠道" id="获取渠道" >[ 获取渠道 ]</a>
### 接口说明
```txt
获取渠道
```
### 定义
```shell
curl -X GET "http://host:port/getChannels
```


### 正确返回
```json
{
	"channels":[
		{
			"id":"id",
			"name":"name"
		}
	],
	"code":0
}
```
### 正确返回参数说明
<table>
<tr>
    <th width="100px">参数名</th><th width="100px">必要参数</th><th width="200px">限制</th><th>说明</th>
</tr>
<tr><td>channels</td><td>必须</td><td> --- </td><td>渠道列表</td><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;id</td><td>必须</td><td> --- </td><td>唯一id</td></tr><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;name</td><td>必须</td><td>长度边界[1 : 200]<br/></td><td>渠道名称</td></tr></tr>
<tr><td>code</td><td>必须</td><td> --- </td><td>状态码, 0：完成</td></tr>
</table>

<a href="#api列表" style="font-size:8px;">返回api列表</a>


## <a name="添加sdk插件" id="添加sdk插件" >[ 添加sdk插件 ]</a>
### 接口说明
```txt
添加sdk插件记录
```
### 定义
```shell
curl -X POST  -d '{
	"desc":"desc",
	"id":"id",
	"name":"name",
	"size":0,
	"startPoint":"startPoint",
	"url":"url",
	"version":0
}' "http://host:port/addSdkPlugin"
```

### 请求参数说明
<table>
<tr>
    <th width="100px">参数名</th><th width="100px">必要参数</th><th width="200px">限制</th><th>说明</th>
</tr>
<tr><td>desc</td><td>必须</td><td>长度边界[1 : 2147483647]<br/></td><td>插件包描述</td></tr>
<tr><td>id</td><td>必须</td><td> --- </td><td>唯一id</td></tr>
<tr><td>name</td><td>必须</td><td>长度边界[1 : 50]<br/></td><td>插件名称</td></tr>
<tr><td>size</td><td>必须</td><td>必须大于或等于0<br/></td><td>插件包大小</td></tr>
<tr><td>startPoint</td><td>必须</td><td>长度边界[1 : 1000]<br/></td><td>启动类的名称</td></tr>
<tr><td>url</td><td>必须</td><td> --- </td><td>插件包的下载url</td></tr>
<tr><td>version</td><td>必须</td><td>必须大于或等于0<br/></td><td>插件版本</td></tr>
</table>

### 正确返回
```json
{
	"code":0
}
```
### 正确返回参数说明
<table>
<tr>
    <th width="100px">参数名</th><th width="100px">必要参数</th><th width="200px">限制</th><th>说明</th>
</tr>
<tr><td>code</td><td>必须</td><td> --- </td><td>状态码, 0：完成</td></tr>
</table>

<a href="#api列表" style="font-size:8px;">返回api列表</a>


## <a name="修改sdk插件" id="修改sdk插件" >[ 修改sdk插件 ]</a>
### 接口说明
```txt
修改sdk插件资料，有无修改的字段都要提交上来
```
### 定义
```shell
curl -X POST  -d '{
	"desc":"desc",
	"id":"id",
	"name":"name",
	"size":0,
	"startPoint":"startPoint",
	"url":"url",
	"version":0
}' "http://host:port/modifySdkPlugin"
```

### 请求参数说明
<table>
<tr>
    <th width="100px">参数名</th><th width="100px">必要参数</th><th width="200px">限制</th><th>说明</th>
</tr>
<tr><td>desc</td><td>必须</td><td>长度边界[1 : 2147483647]<br/></td><td>插件包描述</td></tr>
<tr><td>id</td><td>必须</td><td> --- </td><td>唯一id</td></tr>
<tr><td>name</td><td>必须</td><td>长度边界[1 : 50]<br/></td><td>插件名称</td></tr>
<tr><td>size</td><td>必须</td><td>必须大于或等于0<br/></td><td>插件包大小</td></tr>
<tr><td>startPoint</td><td>必须</td><td>长度边界[1 : 1000]<br/></td><td>启动类的名称</td></tr>
<tr><td>url</td><td>必须</td><td> --- </td><td>插件包的下载url</td></tr>
<tr><td>version</td><td>必须</td><td>必须大于或等于0<br/></td><td>插件版本</td></tr>
</table>

### 正确返回
```json
{
	"code":0
}
```
### 正确返回参数说明
<table>
<tr>
    <th width="100px">参数名</th><th width="100px">必要参数</th><th width="200px">限制</th><th>说明</th>
</tr>
<tr><td>code</td><td>必须</td><td> --- </td><td>状态码, 0：完成</td></tr>
</table>

<a href="#api列表" style="font-size:8px;">返回api列表</a>


## <a name="获取sdk插件列表" id="获取sdk插件列表" >[ 获取sdk插件列表 ]</a>
### 接口说明
```txt
获取整个sdk插件列表
```
### 定义
```shell
curl -X GET "http://host:port/getSdkPlugins
```


### 正确返回
```json
{
	"code":0,
	"sdkPluginsList":[
		{
			"desc":"desc",
			"id":"id",
			"md5":"md5",
			"name":"name",
			"pluginPackageName":"pluginPackageName",
			"size":0,
			"startPoint":"startPoint",
			"url":"url",
			"version":0
		}
	]
}
```
### 正确返回参数说明
<table>
<tr>
    <th width="100px">参数名</th><th width="100px">必要参数</th><th width="200px">限制</th><th>说明</th>
</tr>
<tr><td>code</td><td>必须</td><td> --- </td><td>状态码, 0：完成</td></tr>
<tr><td>sdkPluginsList</td><td>必须</td><td> --- </td><td>sdk插件列表</td><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;desc</td><td>必须</td><td>长度边界[1 : 2147483647]<br/></td><td>插件包描述</td></tr><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;id</td><td>必须</td><td> --- </td><td>唯一id</td></tr><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;md5</td><td>必须</td><td> --- </td><td>插件包的md5计算值</td></tr><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;name</td><td>必须</td><td>长度边界[1 : 50]<br/></td><td>插件名称</td></tr><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;pluginPackageName</td><td>必须</td><td>长度边界[1 : 1000]<br/></td><td>插件的包名</td></tr><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;size</td><td>必须</td><td>必须大于或等于0<br/></td><td>插件包大小</td></tr><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;startPoint</td><td>必须</td><td>长度边界[1 : 1000]<br/></td><td>启动类的名称</td></tr><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;url</td><td>必须</td><td> --- </td><td>插件包的下载url</td></tr><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;version</td><td>必须</td><td>必须大于或等于0<br/></td><td>插件版本</td></tr></tr>
</table>

<a href="#api列表" style="font-size:8px;">返回api列表</a>


## <a name="添加sdk配置" id="添加sdk配置" >[ 添加sdk配置 ]</a>
### 接口说明
```txt
添加sdk配置记录
```
### 定义
```shell
curl -X POST  -d '{
	"brand":"brand",
	"channel":"channel",
	"countryList":[
		0
	],
	"operatorsList":[
		0
	],
	"sdkPluginId":"sdkPluginId",
	"targetPackageName":"targetPackageName"
}' "http://host:port/addSdkConfig"
```

### 请求参数说明
<table>
<tr>
    <th width="100px">参数名</th><th width="100px">必要参数</th><th width="200px">限制</th><th>说明</th>
</tr>
<tr><td>brand</td><td>必须</td><td>必须为以下可用值之一: [ "ALL", "TRANSSION", "OTHERS" ]<br/></td><td>品牌</td></tr>
<tr><td>channel</td><td>必须</td><td> --- </td><td>渠道</td></tr>
<tr><td>countryList</td><td>必须</td><td> --- </td><td>国家列表</td></tr>
<tr><td>operatorsList</td><td>必须</td><td> --- </td><td>运营商列表</td></tr>
<tr><td>sdkPluginId</td><td>必须</td><td> --- </td><td>sdkPlugin的Id</td></tr>
<tr><td>targetPackageName</td><td>可选</td><td> --- </td><td>目标包名</td></tr>
</table>

### 正确返回
```json
{
	"code":0
}
```
### 正确返回参数说明
<table>
<tr>
    <th width="100px">参数名</th><th width="100px">必要参数</th><th width="200px">限制</th><th>说明</th>
</tr>
<tr><td>code</td><td>必须</td><td> --- </td><td>状态码, 0：完成</td></tr>
</table>

<a href="#api列表" style="font-size:8px;">返回api列表</a>


## <a name="删除sdk配置" id="删除sdk配置" >[ 删除sdk配置 ]</a>
### 接口说明
```txt
删除sdk配置记录
```
### 定义
```shell
curl -X POST  -d '{
	"id":"id"
}' "http://host:port/deleteSdkConfig"
```

### 请求参数说明
<table>
<tr>
    <th width="100px">参数名</th><th width="100px">必要参数</th><th width="200px">限制</th><th>说明</th>
</tr>
<tr><td>id</td><td>必须</td><td> --- </td><td>根据id删除</td></tr>
</table>

### 正确返回
```json
{
	"code":0
}
```
### 正确返回参数说明
<table>
<tr>
    <th width="100px">参数名</th><th width="100px">必要参数</th><th width="200px">限制</th><th>说明</th>
</tr>
<tr><td>code</td><td>必须</td><td> --- </td><td>状态码, 0：完成</td></tr>
</table>

<a href="#api列表" style="font-size:8px;">返回api列表</a>


## <a name="检查插件" id="检查插件" >[ 检查插件 ]</a>
### 接口说明
```txt
检查插件是否需要更新
```
### 定义
```shell
curl -X POST  -d '{
	"brand":"brand",
	"channel":"channel",
	"clientVer":"clientVer",
	"imei":"imei",
	"imsi":"imsi",
	"model":"model",
	"packageName":"packageName",
	"pluginsInfo":[
		{
			"pluginPackageName":"pluginPackageName",
			"version":0
		}
	],
	"resolution":"resolution",
	"sdkVer":0
}' "http://host:port/checkSdkPlugins"
```

### 请求参数说明
<table>
<tr>
    <th width="100px">参数名</th><th width="100px">必要参数</th><th width="200px">限制</th><th>说明</th>
</tr>
<tr><td>brand</td><td>必须</td><td> --- </td><td>设备品牌</td></tr>
<tr><td>channel</td><td>必须</td><td> --- </td><td>渠道</td></tr>
<tr><td>clientVer</td><td>必须</td><td> --- </td><td>宿主应用版本号</td></tr>
<tr><td>imei</td><td>必须</td><td>长度边界[15 : 16]<br/></td><td>设备唯一标示</td></tr>
<tr><td>imsi</td><td>必须</td><td>长度边界[15 : 16]<br/></td><td>sim卡唯一标示，没有请上传999999999999999，15个9</td></tr>
<tr><td>model</td><td>必须</td><td> --- </td><td>设备型号</td></tr>
<tr><td>packageName</td><td>必须</td><td> --- </td><td>宿主应用包名</td></tr>
<tr><td>pluginsInfo</td><td>必须</td><td> --- </td><td>插件信息集合</td><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;pluginPackageName</td><td>必须</td><td> --- </td><td>插件的包名</td></tr><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;version</td><td>必须</td><td> --- </td><td>插件版本</td></tr></tr>
<tr><td>resolution</td><td>必须</td><td> --- </td><td>分辨率</td></tr>
<tr><td>sdkVer</td><td>必须</td><td> --- </td><td>sdk版本号，int类型</td></tr>
</table>

### 正确返回
```json
{
	"code":0,
	"interval":0,
	"pluginsInfo":[
		{
			"id":"id",
			"md5":"md5",
			"startPoint":"startPoint",
			"status":"status",
			"url":"url",
			"version":0
		}
	]
}
```
### 正确返回参数说明
<table>
<tr>
    <th width="100px">参数名</th><th width="100px">必要参数</th><th width="200px">限制</th><th>说明</th>
</tr>
<tr><td>code</td><td>必须</td><td> --- </td><td>状态码, 0：完成</td></tr>
<tr><td>interval</td><td>必须</td><td> --- </td><td>下次来更新的时间间隔，单位分钟</td></tr>
<tr><td>pluginsInfo</td><td>必须</td><td> --- </td><td>插件检查结果集合</td><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;id</td><td>必须</td><td> --- </td><td>插件id</td></tr><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;md5</td><td>必须</td><td> --- </td><td>包的md5值</td></tr><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;startPoint</td><td>必须</td><td>长度边界[1 : 1000]<br/></td><td>启动类的名称</td></tr><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;status</td><td>必须</td><td>必须为以下可用值之一: [ "OK", "NEED_UPDATE", "DELETE", "NEW" ]<br/></td><td>OK:已经最新, NEED_UPDATE:需要更新, DELETE:需要删除, NEW:新插件</td></tr><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;url</td><td>必须</td><td> --- </td><td>插件下载url</td></tr><tr><td>
&nbsp;&nbsp;&nbsp;&nbsp;version</td><td>必须</td><td> --- </td><td>插件版本</td></tr></tr>
</table>

<a href="#api列表" style="font-size:8px;">返回api列表</a>





## <a name="#错误码定义" id="错误码定义" >错误码定义</a>
错误码|说明|
:------:|------|
  -3|参数错误
