# HadoopWordCount

Prerequisites: 

        Install Java
        Install Maven
        Install & Start Hadoop :

              http://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-common/SingleCluster.html

            Or 

        Install :   hortonworks-sandbox

              Which is VMWare or VirtualBox Image that comes with whole Hadoop Echo System which includes Hadoop (HDFS), Hive,               Pig, MapRedues, Yarn and Ambari UI, Spark , Kafka and so on.
             
              https://hortonworks.com/tutorial/hortonworks-sandbox-guide/
      
 
 Create Map Reduce Jar:
 
             i)  Clone the Soucecode
             ii)  mvn clean packge

 SFTP the Jar to the VM where you have the Hadoop by using FileZilla or Terminal
 
            ssh venky@VM 
            
  Create the Sample Data in HDFS :
          
          Create two file in local file system as follows /usr/venky/wordcount/input
              file01.txt 
                  Hello World Bye World 
                  
               file01.txt    
                   Hello Hadoop Goodbye Hadoop
           
           Put these Files in HDFS
           
               Make new HDFS Folder
                  hadoop fs -mkdir /usr/venky/wordcount/input
               
               Put the above created Txt Files
               
                  hadoop fs -put /user/venky/wordcount/input/*.txt /user/venky/wordcount/input
               
           Execute the MapReduce Program:
                Navigate to the folder where have your wordcount-0.jar file
                
                 set $CLASSPTH=.:$CALSSPATH   
                 hadoop jar wordcount-0.jar org.WordCount /user/venky/wordcount/input/*.txt /user/venky/wordcount/output/
           
                  Check the output folder /user/venky/wordcount/output/, you can see two files 
                 
                   You can see the result as follows.
                   
                      Bye	1
                      Goodbye	1
                      Hadoop	2
                      Hello	2
                      World	2


           
           
           
           
           
           
           
           
               
               
               
               
               
               
               
               
               
               
               
     
    
  
