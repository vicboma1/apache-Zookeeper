# Apache-Zookeeper

## Requeriments on Mac

### Install brew
```
vicboma:Documents vicboma$> /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Install gcc
```
vicboma:Documents vicboma$>  brew install gcc
```

### Install gradle
```
vicboma:Documents vicboma$>  brew install gradle 
or
vicboma:Documents vicboma$>  brew upgrate gradle

vicboma:Documents vicboma$> gradle -v

------------------------------------------------------------
Gradle 6.2
------------------------------------------------------------

Build time:   2020-02-17 08:32:01 UTC
Revision:     61d3320259a1a0d31519bf208eb13741679a742f

Kotlin:       1.3.61
Groovy:       2.5.8
Ant:          Apache Ant(TM) version 1.10.7 compiled on September 1 2019
JVM:          13.0.2 (Oracle Corporation 13.0.2+8)
OS:           Mac OS X 10.14.3 x86_64

```

### Install apache-zookeeper
```
vicboma:Documents vicboma$>  wget https://downloads.apache.org/zookeeper/zookeeper-3.5.7/apache-zookeeper-3.5.7-bin.tar.gz
vicboma:Documents vicboma$>  tar -xvzf apache-zookeeper-3.5.7-bin.tar.gz
```


## Configuration Standalone-Mode

### Properties 'zoo.conf'
```
vicboma:Documents vicboma$>  cd apache-zookeeper-3.5.7-bin/conf
vicboma:conf vicboma$>  vi zoo_sample.cfg

'''
# The number of milliseconds of each tick
tickTime=2000
# The number of ticks that the initial
# synchronization phase can take
initLimit=10
# The number of ticks that can pass between
# sending a request and getting an acknowledgement
syncLimit=5
# the directory where the snapshot is stored.
# do not use /tmp for storage, /tmp here is just
# example sakes.
dataDir=/tmp/zookeeper
# the port at which the clients will connect
clientPort=2181
'''

vicboma:conf vicboma$> cp zoo_sample.cfg zoo.cfg
```

### Start Standalone-Mode
```
vicboma:conf vicboma$> cd ..
vicboma:apache-zookeeper-3.5.7-bin vicboma$> cd bin
vicboma:bin vicboma$> ./zkCli.sh -server 127.0.0.1:2181
/usr/bin/java
Connecting to 127.0.0.1:2181
2020-02-23 21:29:15,840 [myid:] - INFO  [main:Environment@109] - Client environment:zookeeper.version=3.5.7-f0fdd52973d373ffd9c86b81d99842dc2c7f660e, built on 02/10/2020 11:30 GMT
2020-02-23 21:29:15,844 [myid:] - INFO  [main:Environment@109] - Client environment:host.name=192.168.1.37
2020-02-23 21:29:15,844 [myid:] - INFO  [main:Environment@109] - Client environment:java.version=9
2020-02-23 21:29:15,847 [myid:] - INFO  [main:Environment@109] - Client environment:java.vendor=Oracle Corporation
2020-02-23 21:29:15,847 [myid:] - INFO  [main:Environment@109] - Client environment:java.home=/Library/Java/JavaVirtualMachines/jdk-9.jdk/Contents/Home
2020-02-23 21:29:15,847 [myid:] - INFO  [main:Environment@109] - Client environment:java.class.path=/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../zookeeper-server/target/classes:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../build/classes:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../zookeeper-server/target/lib/*.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../build/lib/*.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/zookeeper-jute-3.5.7.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/zookeeper-3.5.7.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/slf4j-log4j12-1.7.25.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/slf4j-api-1.7.25.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/netty-transport-native-unix-common-4.1.45.Final.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/netty-transport-native-epoll-4.1.45.Final.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/netty-transport-4.1.45.Final.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/netty-resolver-4.1.45.Final.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/netty-handler-4.1.45.Final.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/netty-common-4.1.45.Final.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/netty-codec-4.1.45.Final.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/netty-buffer-4.1.45.Final.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/log4j-1.2.17.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/json-simple-1.1.1.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jline-2.11.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jetty-util-9.4.24.v20191120.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jetty-servlet-9.4.24.v20191120.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jetty-server-9.4.24.v20191120.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jetty-security-9.4.24.v20191120.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jetty-io-9.4.24.v20191120.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jetty-http-9.4.24.v20191120.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/javax.servlet-api-3.1.0.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jackson-databind-2.9.10.2.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jackson-core-2.9.10.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jackson-annotations-2.9.10.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/commons-cli-1.2.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/audience-annotations-0.5.0.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../zookeeper-*.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../zookeeper-server/src/main/resources/lib/*.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../conf:
2020-02-23 21:29:15,848 [myid:] - INFO  [main:Environment@109] - Client environment:java.library.path=/Users/vicboma/Library/Java/Extensions:/Library/Java/Extensions:/Network/Library/Java/Extensions:/System/Library/Java/Extensions:/usr/lib/java:.
2020-02-23 21:29:15,848 [myid:] - INFO  [main:Environment@109] - Client environment:java.io.tmpdir=/var/folders/51/nq741rk167b9n56nglkbxxd40000gn/T/
2020-02-23 21:29:15,848 [myid:] - INFO  [main:Environment@109] - Client environment:java.compiler=<NA>
2020-02-23 21:29:15,848 [myid:] - INFO  [main:Environment@109] - Client environment:os.name=Mac OS X
2020-02-23 21:29:15,848 [myid:] - INFO  [main:Environment@109] - Client environment:os.arch=x86_64
2020-02-23 21:29:15,849 [myid:] - INFO  [main:Environment@109] - Client environment:os.version=10.14.3
2020-02-23 21:29:15,849 [myid:] - INFO  [main:Environment@109] - Client environment:user.name=vicboma
2020-02-23 21:29:15,849 [myid:] - INFO  [main:Environment@109] - Client environment:user.home=/Users/vicboma
2020-02-23 21:29:15,849 [myid:] - INFO  [main:Environment@109] - Client environment:user.dir=/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin
2020-02-23 21:29:15,849 [myid:] - INFO  [main:Environment@109] - Client environment:os.memory.free=247MB
2020-02-23 21:29:15,851 [myid:] - INFO  [main:Environment@109] - Client environment:os.memory.max=256MB
2020-02-23 21:29:15,852 [myid:] - INFO  [main:Environment@109] - Client environment:os.memory.total=256MB
2020-02-23 21:29:15,855 [myid:] - INFO  [main:ZooKeeper@868] - Initiating client connection, connectString=127.0.0.1:2181 sessionTimeout=30000 watcher=org.apache.zookeeper.ZooKeeperMain$MyWatcher@1a38c59b
2020-02-23 21:29:15,941 [myid:] - INFO  [main:X509Util@79] - Setting -D jdk.tls.rejectClientInitiatedRenegotiation=true to disable client-initiated TLS renegotiation
2020-02-23 21:29:15,955 [myid:] - INFO  [main:ClientCnxnSocket@237] - jute.maxbuffer value is 4194304 Bytes
2020-02-23 21:29:15,964 [myid:] - INFO  [main:ClientCnxn@1653] - zookeeper.request.timeout value is 0. feature enabled=
Welcome to ZooKeeper!
2020-02-23 21:29:16,021 [myid:127.0.0.1:2181] - INFO  [main-SendThread(127.0.0.1:2181):ClientCnxn$SendThread@1112] - Opening socket connection to server localhost/127.0.0.1:2181. Will not attempt to authenticate using SASL (unknown error)
JLine support is enabled
2020-02-23 21:29:16,046 [myid:127.0.0.1:2181] - INFO  [main-SendThread(127.0.0.1:2181):ClientCnxn$SendThread@959] - Socket connection established, initiating session, client: /127.0.0.1:51520, server: localhost/127.0.0.1:2181
[zk: 127.0.0.1:2181(CONNECTING) 0] 2020-02-23 21:29:16,469 [myid:127.0.0.1:2181] - INFO  [main-SendThread(127.0.0.1:2181):ClientCnxn$SendThread@1394] - Session establishment complete on server localhost/127.0.0.1:2181, sessionid = 0x10000684b0b0000, negotiated timeout = 30000

WATCHER::

WatchedEvent state:SyncConnected type:None path:null

[zk: 127.0.0.1:2181(CONNECTED) 0] help
ZooKeeper -server host:port cmd args
	addauth scheme auth
	close 
	config [-c] [-w] [-s]
	connect host:port
	create [-s] [-e] [-c] [-t ttl] path [data] [acl]
	delete [-v version] path
	deleteall path
	delquota [-n|-b] path
	get [-s] [-w] path
	getAcl [-s] path
	history 
	listquota path
	ls [-s] [-w] [-R] path
	ls2 path [watch]
	printwatches on|off
	quit 
	reconfig [-s] [-v version] [[-file path] | [-members serverID=host:port1:port2;port3[,...]*]] | [-add serverId=host:port1:port2;port3[,...]]* [-remove serverId[,...]*]
	redo cmdno
	removewatches path [-c|-d|-a] [-l]
	rmr path
	set [-s] [-v version] path data
	setAcl [-s] [-v version] [-R] path acl
	setquota -n|-b val path
	stat [-w] path
	sync path

[zk: 127.0.0.1:2181(CONNECTED) 1] ls /
[zookeeper]

[zk: 127.0.0.1:2181(CONNECTED) 2] create /zk_test my_data
Created /zk_test

[zk: 127.0.0.1:2181(CONNECTED) 3] ls /
[zk_test, zookeeper]

[zk: 127.0.0.1:2181(CONNECTED) 4] get /zk_test
my_data

[zk: 127.0.0.1:2181(CONNECTED) 5] set /zk_test junk

[zk: 127.0.0.1:2181(CONNECTED) 6] get /zk_test
junk

[zk: 127.0.0.1:2181(CONNECTED) 7] ls /zk_test
[]

[zk: 127.0.0.1:2181(CONNECTED) 8] delete /zk_test

[zk: 127.0.0.1:2181(CONNECTED) 9] ls /
[zookeeper]
```

### 

## Configuration Replicated-Mode

### Properties 'zoo.conf'
```
vicboma:Documents vicboma$>  cd apache-zookeeper-3.5.7-bin/conf
vicboma:conf vicboma$>  vi zoo_sample.cfg

'''
tickTime=2000
dataDir=/var/lib/zookeeper
clientPort=2182
initLimit=5
syncLimit=2
server.1=zoo1:2888:3888
server.2=zoo2:2888:3888
server.3=zoo3:2888:3888
'''

vicboma:conf vicboma$> cp zoo_sample.cfg zoo.cfg
```

### Start Replicated-Mode
```
vicboma:conf vicboma$> cd ..
vicboma:apache-zookeeper-3.5.7-bin vicboma$> cd bin
vicboma:bin vicboma$ ./zkCli.sh -server 127.0.0.1:2182
/usr/bin/java

Connecting to 127.0.0.1:2182
2020-02-23 22:19:36,862 [myid:] - INFO  [main:Environment@109] - Client environment:zookeeper.version=3.5.7-f0fdd52973d373ffd9c86b81d99842dc2c7f660e, built on 02/10/2020 11:30 GMT
2020-02-23 22:19:36,866 [myid:] - INFO  [main:Environment@109] - Client environment:host.name=192.168.1.37
2020-02-23 22:19:36,867 [myid:] - INFO  [main:Environment@109] - Client environment:java.version=9
2020-02-23 22:19:36,869 [myid:] - INFO  [main:Environment@109] - Client environment:java.vendor=Oracle Corporation
2020-02-23 22:19:36,870 [myid:] - INFO  [main:Environment@109] - Client environment:java.home=/Library/Java/JavaVirtualMachines/jdk-9.jdk/Contents/Home
2020-02-23 22:19:36,870 [myid:] - INFO  [main:Environment@109] - Client environment:java.class.path=/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../zookeeper-server/target/classes:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../build/classes:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../zookeeper-server/target/lib/*.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../build/lib/*.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/zookeeper-jute-3.5.7.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/zookeeper-3.5.7.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/slf4j-log4j12-1.7.25.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/slf4j-api-1.7.25.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/netty-transport-native-unix-common-4.1.45.Final.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/netty-transport-native-epoll-4.1.45.Final.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/netty-transport-4.1.45.Final.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/netty-resolver-4.1.45.Final.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/netty-handler-4.1.45.Final.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/netty-common-4.1.45.Final.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/netty-codec-4.1.45.Final.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/netty-buffer-4.1.45.Final.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/log4j-1.2.17.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/json-simple-1.1.1.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jline-2.11.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jetty-util-9.4.24.v20191120.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jetty-servlet-9.4.24.v20191120.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jetty-server-9.4.24.v20191120.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jetty-security-9.4.24.v20191120.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jetty-io-9.4.24.v20191120.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jetty-http-9.4.24.v20191120.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/javax.servlet-api-3.1.0.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jackson-databind-2.9.10.2.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jackson-core-2.9.10.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/jackson-annotations-2.9.10.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/commons-cli-1.2.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../lib/audience-annotations-0.5.0.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../zookeeper-*.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../zookeeper-server/src/main/resources/lib/*.jar:/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin/../conf:
2020-02-23 22:19:36,870 [myid:] - INFO  [main:Environment@109] - Client environment:java.library.path=/Users/vicboma/Library/Java/Extensions:/Library/Java/Extensions:/Network/Library/Java/Extensions:/System/Library/Java/Extensions:/usr/lib/java:.
2020-02-23 22:19:36,871 [myid:] - INFO  [main:Environment@109] - Client environment:java.io.tmpdir=/var/folders/51/nq741rk167b9n56nglkbxxd40000gn/T/
2020-02-23 22:19:36,871 [myid:] - INFO  [main:Environment@109] - Client environment:java.compiler=<NA>
2020-02-23 22:19:36,871 [myid:] - INFO  [main:Environment@109] - Client environment:os.name=Mac OS X
2020-02-23 22:19:36,871 [myid:] - INFO  [main:Environment@109] - Client environment:os.arch=x86_64
2020-02-23 22:19:36,871 [myid:] - INFO  [main:Environment@109] - Client environment:os.version=10.14.3
2020-02-23 22:19:36,872 [myid:] - INFO  [main:Environment@109] - Client environment:user.name=vicboma
2020-02-23 22:19:36,872 [myid:] - INFO  [main:Environment@109] - Client environment:user.home=/Users/vicboma
2020-02-23 22:19:36,872 [myid:] - INFO  [main:Environment@109] - Client environment:user.dir=/Users/vicboma/Documents/apache-kafka/kafka-2.4.0-src/bin/apache-zookeeper-3.5.7-bin/bin
2020-02-23 22:19:36,872 [myid:] - INFO  [main:Environment@109] - Client environment:os.memory.free=247MB
2020-02-23 22:19:36,874 [myid:] - INFO  [main:Environment@109] - Client environment:os.memory.max=256MB
2020-02-23 22:19:36,874 [myid:] - INFO  [main:Environment@109] - Client environment:os.memory.total=256MB
2020-02-23 22:19:36,878 [myid:] - INFO  [main:ZooKeeper@868] - Initiating client connection, connectString=127.0.0.1:2182 sessionTimeout=30000 watcher=org.apache.zookeeper.ZooKeeperMain$MyWatcher@1a38c59b
2020-02-23 22:19:36,884 [myid:] - INFO  [main:X509Util@79] - Setting -D jdk.tls.rejectClientInitiatedRenegotiation=true to disable client-initiated TLS renegotiation
2020-02-23 22:19:36,897 [myid:] - INFO  [main:ClientCnxnSocket@237] - jute.maxbuffer value is 4194304 Bytes
2020-02-23 22:19:36,907 [myid:] - INFO  [main:ClientCnxn@1653] - zookeeper.request.timeout value is 0. feature enabled=
Welcome to ZooKeeper!
2020-02-23 22:19:36,932 [myid:127.0.0.1:2182] - INFO  [main-SendThread(127.0.0.1:2182):ClientCnxn$SendThread@1112] - Opening socket connection to server localhost/127.0.0.1:2182. Will not attempt to authenticate using SASL (unknown error)
JLine support is enabled
WATCHER::

WatchedEvent state:SyncConnected type:None path:null

[zk: 127.0.0.1:2182(CONNECTED) 0] help
ZooKeeper -server host:port cmd args
	addauth scheme auth
	close 
	config [-c] [-w] [-s]
	connect host:port
	create [-s] [-e] [-c] [-t ttl] path [data] [acl]
	delete [-v version] path
	deleteall path
	delquota [-n|-b] path
	get [-s] [-w] path
	getAcl [-s] path
	history 
	listquota path
	ls [-s] [-w] [-R] path
	ls2 path [watch]
	printwatches on|off
	quit 
	reconfig [-s] [-v version] [[-file path] | [-members serverID=host:port1:port2;port3[,...]*]] | [-add serverId=host:port1:port2;port3[,...]]* [-remove serverId[,...]*]
	redo cmdno
	removewatches path [-c|-d|-a] [-l]
	rmr path
	set [-s] [-v version] path data
	setAcl [-s] [-v version] [-R] path acl
	setquota -n|-b val path
	stat [-w] path
	sync path

[zk: 127.0.0.1:2182(CONNECTED) 1] ls /
[zookeeper]

[zk: 127.0.0.1:2182(CONNECTED) 2] create /zk_test my_data
Created /zk_test

[zk: 127.0.0.1:2182(CONNECTED) 3] ls /
[zk_test, zookeeper]

[zk: 127.0.0.1:2182(CONNECTED) 4] get /zk_test
my_data

[zk: 127.0.0.1:2182(CONNECTED) 5] set /zk_test junk

[zk: 127.0.0.1:2182(CONNECTED) 6] get /zk_test
junk

[zk: 127.0.0.1:2182(CONNECTED) 7] ls /zk_test
[]

[zk: 127.0.0.1:2182(CONNECTED) 8] delete /zk_test

[zk: 127.0.0.1:2182(CONNECTED) 9] ls /
[zookeeper]
```

### 
