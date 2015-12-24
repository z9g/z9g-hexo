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
- [iOS 持续集成](http://blog.lanvige.com/2015/07/13/ios-ci-solution/)
- [Phabricator 安装及使用指南](http://wenku.baidu.com/link?url=eTO2B-pOEzh7liswKrjLxCEJ5vni6nemL52FLujWd151zYrlooP3Vll2Vi9eGqn2UZldvjllYFJTcRaRUJhnlqZyWLn8QdNwKwScYeGzXVO)

## Viedos
- [Continuous Integration with Jenkins and Docker (part 1)](https://www.youtube.com/watch?v=ppCzDDpcqRk)
- [Run Jenkins in Slave Master Config in Docker](https://www.youtube.com/watch?v=dwomWpJ0m3g)
