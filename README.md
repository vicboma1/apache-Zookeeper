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

$> gradle -v
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
