1.配置ssh免密码登陆

2.hadoop-2.7.5
	
	1>.创建在hadoop配置中新增的目录
	2>.格式化HDFS

3.spark-2.0.0
	
	1>.安装spark前先安装scala-2.11
	2>.spark-env.sh 中SPARK_LOCAL_IP为外网ip;
	3>.在HDFS上创建目录spark-defaults.conf中的spark.eventLog.dir, 并修改权限.
	4>.可以查看运行时的log, 确认master和slave成功运行.

4.hive-2.1.1

	1>.修改好hive-site.xml后, 将MySQL驱动包(mysql-connector-java-5.1.46.jar)拷贝到Hive的lib目录下
	2>.如果metastore是mysql, 使用hive前先初始化
	$ schematool  -initSchema  -dbType  mysql  
	3>. 开启hive服务,以便spark等连接hive
	$ hive --service metastore 

5.hbase-1.4.6

	1>.目前采用伪分布式配置

6.配置上面的东西后, 检查是否按profile.txt中配置设置环境变量.HADOOP_CLASSPATH和SPARK_CLASSPATH影响较大.
