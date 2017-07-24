# tispark
A thin layer of TiSpark. Most of the logic is inside tikv-java-client library.
https://github.com/pingcap/tikv-client-lib-java


Uses as below
```
./spark-shell --jars /where-ever-it-is/tispark-0.1.0-SNAPSHOT-jar-with-dependencies.jar

import org.apache.spark.sql.TiContext

val ti = new TiContext(spark, List("127.0.0.1:" + 2379))

ti.tidbMapDatabase("tpch")

spark.sql("select count(*) from test").show
