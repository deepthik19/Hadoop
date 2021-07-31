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
