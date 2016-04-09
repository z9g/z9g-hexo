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

codesign -f -s cert xx.app/appex/dylib
xcrun -sdk iphoneos PackageApplication -v WeChat.app  -o ~/WeChat.ipa
```

# References
- [Building Gradle Projects with Jenkins CI](https://github.com/codepath/android_guides/wiki/Building-Gradle-Projects-with-Jenkins-CI)
- [Building Android Projects with Gradle](https://spring.io/guides/gs/gradle-android/)
- [android--jenkins+gradle+android自动化构建apk步骤](http://blog.csdn.net/ymlxku/article/details/39962481)

- [CI第一篇:Jenkins+github->fir.im/蒲公英pgyer.com](http://www.jianshu.com/p/a501153c9d59)
- [用 Jenkins 自动化构建 Android 和 iOS 应用](http://android.jobbole.com/82423/)
- [一步一步构建iOS持续集成:Jenkins+GitLab+蒲公英+FTP](http://www.jianshu.com/p/c69deb29720d)
- [An Easy Way to Make an iOS Build for TestFlight Using Jenkins](http://blog.zymr.com/jenkins-integration-with-ios-3)
- [Jenkins: Setting Up iOS Code Signing](http://www.egeek.me/2015/04/12/jenkins-setting-up-ios-code-signing/)
