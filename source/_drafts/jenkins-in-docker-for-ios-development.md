# [Homebrew](http://brew.sh/)

```bash
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

# docker

```
$ brew cask install dockertoolbox

$ docker-machine create --driver virtualbox default
$ docker-machine ls
$ docker-machine env default
$ eval "$(docker-machine env default)"

$ docker run hello-world
```

# jenkins

```
$ docker pull jenkins
$ docker load -i jenkins.tar

$ VBoxManage controlvm "default" natpf1 "tcp-port8080,tcp,,8080,,8080"
```

# Xcode

```
$ xcode-select --install
```


# References
- [PUTTING JENKINS IN A DOCKER CONTAINER](https://engineering.riotgames.com/news/putting-jenkins-docker-container)
- [Port forwarding in docker-machine?](http://stackoverflow.com/questions/32174560/port-forwarding-in-docker-machine)
- [Jenkins in a Docker container](http://dertompson.com/2014/09/01/jenkins-in-a-docker-container/)
- [Jenkins iOS – Git, xcodebuild, TestFlight](http://blog.iteedee.com/2014/01/jenkins-ios-git-xcodebuild-test-flight/)
