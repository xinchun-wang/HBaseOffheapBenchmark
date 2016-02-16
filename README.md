# HBase Offheap Benchmark

测试HBase1.1 下使用BucketCache的时候在随机读的性能表现。

#测试环境
##硬件：
CPU: Intel(R) Xeon(R) CPU E5-2640 v2 @ 2.00GHz

Memory:64G

Disk: Intel DC S3500 SSD 6*300G 

Net: 1G*2 Bound

##软件
Hadoop 2.7.2 

HBase 1.1.3

JDK 1.7.0_79

##测试环境设置
3台 Server HDFS，挂载5块SSD硬盘

hdfs-site.xml部分配置

  <property>
    <name>dfs.replication</name>
    <value>3</value>
  </property>
  
  <property>
    <name>dfs.blocksize</name>
    <value>134742016</value>
  </property>
  
  <property>
    <name>dfs.datanode.max.transfer.threads</name>
    <value>2048</value>
  </property>
  
  <property>
    <name>dfs.datanode.handler.count</name>
    <value>16</value>
  </property>
  
   <property>
    <name>dfs.datanode.data.dir</name>
    <value>/data01/dfs/data,/data02/dfs/data,/data03/dfs/data,/data04/dfs/data,/data05/dfs/data</value>
    <final>true</final>
  </property>
  
  
 1台Region Server
 
 1台 YCSB 测试Client
