<b> Step by step approach for setting up Pseudo-distributed mode on OS X El Capitan. </b>

1. Check if Java is installed. 

        $ java -version
        java version "1.8.0_92"
        Java(TM) SE Runtime Environment (build 1.8.0_92-b14)
        Java HotSpot(TM) 64-Bit Server VM (build 25.92-b14, mixed mode)

    Optional - 

        $ javac -version
        javac 1.8.0_92

2. Enable SSH 

  a. System Preferences -> Sharing -> Tick Remote Login 
  //optional_instructions_to_add

  b.Check if you can access ssh to localhost without any passphrase - 
  
       $ ssh localhost

  If not, run - 

      $ ssh-keygen -t dsa -P '' -f ~/.ssh/id_dsa
      $ cat ~/.ssh/id_dsa.pub >> ~/.ssh/authorized_keys

3. Download Hadoop Common Distribution [Link](http://www.apache.org/dyn/closer.cgi/hadoop/common/) 
  
  Download hadoop-[version].tar.gz and unpack to any directory. 

4. Directory/etc/hadoop/hadoop-env.sh 

  Change - 
  
      export JAVA_HOME={Java_Home_Directory} 
      export HADOOP_HOME = /Users/kshah/Documents/hadoop-2.7.2/ {Hadoop_Directory}
  
  Note - Java home directory can be found by: 
  
      $ /usr/libexec/java_home
      /Library/Java/JavaVirtualMachines/jdk1.8.0_92.jdk/Contents/Home

  
    <b>References</b> - 
    [Hadoop Wiki](https://wiki.apache.org/hadoop/Running_Hadoop_On_OS_X_10.5_64-bit_(Single-Node_Cluster))
