# sample


##传统方式
```powershell
#安装git
yum install -y git
#下载jre，必须从页面获取下载地址后下载
#https://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html
#下载完后安装
yum install jre-8u201-linux-x64.rpm

git clone https://github.com/jockey1230/sample.git

#启动user服务,指定hostname=localhost
nohup java -jar -Ddetail.hostname=localhost ./user/user-0.0.1-SNAPSHOT.jar >/dev/null 2>&1 &

#启动detail服务
nohup java -jar ./detail/detail-0.0.1-SNAPSHOT.jar >/dev/null 2>&1 &

#等待服务启动完成（30秒左右）,访问user接口
curl http://localhost:8080/user
#返回
username is admin
```

##微服务方式
```powershell
#将jar包打包成镜像
cd user
docker build -t user:latest .
cd ..
cd detail
docker build -t detail:latest .

kubectl apply -f ./user.yml

curl http://localhost/user

```


