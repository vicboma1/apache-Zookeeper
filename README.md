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


## Configuration

### Properties 'zoo.conf'
```
vicboma:Documents vicboma$>  cd apache-zookeeper-3.5.7-bin/conf
vicboma:Documents vicboma$>  vi zoo_sample.cfg

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

