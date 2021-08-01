# Hadoop
Hadoop setup project
Prequite: Java 8 nstalled
Download HADOOP binary from https://hadoop.apache.org/releases.html (version one less than latest)
Unzip and name the folder as 'hadoop'
Create new folder 'data' under hadoop
Create 2 more folders 'datanode' and 'namenode' under data folder
Now update config properties in the below files in hadoop/etc/hadoop. Take the files committed above
1. core-site.xml
2. hdfs-site.xml
3. mapred-site.xml
4. yarn-site.xml
5. Also update JAVAHOME path in hadoop-env.cmd

Now set the environment variables:
1. Add new Variable -> HADOOP_HOME with path to bin folder
2. Edit Path variable and add path to bin and sbin folders

Finally replace your bin folder with the bin folder contents downloaded from here

To check hadoop is installed right:
Open command prompt and run:
>hadoop

>hdfs namenode -format

If you see no errors, everything is fine

Now to start hadoop:
In cmd, go to hadoop directory and run below commands.

>etc\hadoop\hadoop-env.cmd
>sbin\start-dfs.cmd
>sbin\start-yarn.cmd

Validate by opening below URLs in browser:
http://localhost:8088/
http://localhost:9870/ -> Utilities -> Browse the file system for checking hdfs file system
For logs: http://localhost:9870/logs/userlogs/

To run the java application for MapReduce:

Create input folder on hdfs to upload input csv/txt files unsing cmd.
>hdfs dfs -mkdir -p user/Deepthi/input/
>hdfs dfs -copyFromLocal C:/geosales.csv user/Deepthi/input
>hdfs dfs -ls user/Deepthi/input
Found 1 items
-rw-r--r--   1 Deepthi supergroup   14873825 2021-08-01 20:27 user/Deepthi/input/geosales.csv

Below command can be used to remove an files/jar/csv/etc
>hdfs dfs -rm input


In cmd, go to the directory where the application jar is present and run (hadoop <app jar name> <input file path with name in hdfs file system> <path of output directory where we wnat our output to be saved>):

>hadoop jar Testing3.jar /user/Deepthi/geosales.csv /user/Deepthi/user/Deepthi/output
