# sample


##启动user服务
java -jar -Ddetail.hostname=localhost ./user-0.0.1-SNAPSHOT.jar &
##启动detail服务
java -jar ./detail-0.0.1-SNAPSHOT.jar