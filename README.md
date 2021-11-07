# wlsEnv
weblogic 复现用

# 说明
存一点jar包，环境可用这个搭建https://github.com/QAX-A-Team/WeblogicEnvironment

JDK安装包下载地址：https://www.oracle.com/technetwork/java/javase/archive-139210.html    
Weblogic安装包下载地址：https://www.oracle.com/technetwork/middleware/weblogic/downloads/wls-for-dev-1703574.html



# 远程调试

修改 `/root/Oracle/Middleware/user_projects/domains/base_domain/bin/setDomainEnv.sh` 在上方加入两行debug配置,然后就可以像普通项目一样正常debug了

```
debugFlag="true"
export debugFlag
```

# 获取jar
```bash

cd /root/Oracle/Middleware 

mkdir test
find ./ -name "*.jar" -exec cp {} ./test/ \;
find ./ -name "*.war" -exec cp {} ./test/ \;

tar cvf jar.tar ./test/
```

# cve

基于T3协议漏洞： CVE-2015-4582、CVE-2016-0638、CVE-2016-3510、CVE-2018-2628、CVE-2020-2555、CVE-2020-2883    
基于XML:CVE-2017-3506、CVE-2017-10271、CVE-2019-2729    
除此之外还有一些SSRF和任意文件上传
