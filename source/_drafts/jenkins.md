title: Jenkins
tags:
---

# Java

```
brew cask install java
```

# Jenkins

```
brew install jenkins
launchctl load /usr/local/opt/jenkins/homebrew.mxcl.jenkins.plist
```

# Android

```
brew install android-sdk
export ANDROID_HOME=/usr/local/opt/android-sdk

brew install homebrew/versions/gradle24

cd /path/to/your/project/
gradle clean
gradle assemble
```

# iOS

```
xcodebuild -version
xcodebuild -showsdks

cd /path/to/your/project/
xcodebuild -list
xcodebuild -target xxx
xcodebuild -target xxx -configuration Debug
xcodebuild clean
```

# References
- [Building Gradle Projects with Jenkins CI](https://github.com/codepath/android_guides/wiki/Building-Gradle-Projects-with-Jenkins-CI)
- [Building Android Projects with Gradle](https://spring.io/guides/gs/gradle-android/)
