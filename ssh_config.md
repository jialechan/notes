### 配置私钥
1. 使用命令ssh-keygen -t rsa -f myfile生成密钥   
-t 表示加密类型   
-f 设置文件明   
   
会生成一个私钥和一个公钥，（在提示输入passphrase时如果不输入，直接回车，那么以后你登录服务器就不会验证密码，否则会要求你输入passphrase）   
   
私钥放在当前目录:myfile   
公钥放在当前目录:myfile.pub   
   
2. 将公钥拷贝到远程服务器上的/root/.ssh/authorized_keys文件
(scp /root/.ssh/id_rsa.pub server:/root/.ssh/authorized_keys)，注意，文件名一定要叫authorized_keys。

3. 客户端上保留私钥，公钥留不留都可以。也就是服务器上要有公钥，客户端上要有私钥。这样就可以实现无密码验证登录了。

### 禁止口令登录，
可以修改/etc/ssh/sshd_conf中的  
PasswordAuthentication yes 改为  
PasswordAuthentication no  
也即只能使用密匙认证的openssh，禁止使用口令认证。  
重启sshd: service sshd restart

### 遇到问题时
```shell
restorecon -Rv /root/.ssh
```
或者可以救到你，参考：https://serverfault.com/questions/55343/cant-get-ssh-public-key-authentication-to-work
   
ssh断开      
修改/etc/ssh/sshd_config配置文件，找到ClientAliveCountMax（单位为分钟）修改你想要的值，执行service sshd reload 
