## Hive Metastore Libs

This project just assemble hive metastore libs for spark sql hive metastore client initialization.

reference to [spark-plugins](https://github.com/zhuguangbin/spark-plugins#how-to)

````
# local_hive1 as external catalog
spark.sql.catalog.local_hive1						cn.com.bigdata123.spark.plugin.catalog.hive.V2ExternalCatalog
# put local hive 1.2.1 hive-site.xml to SPARK_CONF_DIR, rename it to hive-site.{CATALOG_NAME}.xml
spark.sql.catalog.local_hive1.hive-site-file				hive-site.local_hive1.xml
spark.sql.catalog.local_hive1.spark.sql.hive.metastore.version  		1.2.1
spark.sql.catalog.local_hive1.spark.sql.hive.metastore.jars             	path
spark.sql.catalog.local_hive1.spark.sql.hive.metastore.jars.path		hdfs://localhost:8020/data/spark/lib/hive-metastore-libs/hive-metastore-libs-1.2.1-assemble.jar
# otherwise we must use a bunch of local jar files, when yarn cluster mode, these jars should be installed at every yarn NodeManger node
#spark.sql.catalog.local_hive1.spark.sql.hive.metastore.jars.path        	file:///opt/hive-1.2.1/lib/*.jar,file:///opt/hadoop/share/hadoop/common/*.jar,file:///opt/hadoop/share/hadoop/common/lib/*.jar,file:///opt/hadoop/share/hadoop/hdfs/*.jar,file:///opt/hadoop/share/hadoop/hdfs/lib/*.jar,file:///opt/hadoop/share/hadoop/yarn/*.jar,file:///opt/hadoop/share/hadoop/yarn/lib/*.jar,file:///opt/hadoop/share/hadoop/mapreduce/*.jar,file:///opt/hadoop/share/hadoop/mapreduce/lib/*.jar
````

We support 2 hive versions:

* 1.2.1

``
mvn clean package -P1.2.1
``

* 2.3.6

``
mvn clean package -P2.3.6
``


