title: iOSRE
tags:
---

# theos

```
make update-theos
```

# resign

- [代码签名探析](http://objccn.io/issue-17-2/)
- [最简单的重签名应用的方法](http://bbs.iosre.com/t/topic/2966)
- [一步一步实现iOS微信自动抢红包(非越狱)](http://www.jianshu.com/p/189afbe3b429)
- [Resigning iOS App IPA with multiple targets and provisioning profiles](https://medium.com/@ssowonny/resigning-ios-app-ipa-with-multiple-targets-and-provisioning-profiles-d868e5a9f70f#.cg0uby8w9)

# App Hook

- [iOS冰与火之歌番外篇 - 在非越狱手机上进行App Hook](http://drops.wooyun.org/papers/12803)

# WeChat

```
Payload/WeChat.app/Info.plist
138     <key>CFBundleIdentifier</key>
139     <string>com.tencent.xin1</string>

Payload/WeChat.app/Watch/WeChatWatchNative.app/Info.plist
 29     <key>CFBundleIdentifier</key>
 30     <string>com.tencent.xin.watchapp1</string>
...
 74     <key>WKCompanionAppBundleIdentifier</key>
 75     <string>com.tencent.xin1</string>

Payload/WeChat.app/PlugIns/WeChatShareExtensionNew.appex/Info.plist
 13     <key>CFBundleIdentifier</key>
 14     <string>com.tencent.xin.sharetimeline1</string>

Payload/WeChat.app/Watch/WeChatWatchNative.app/PlugIns/WeChatWatchNativeExtension.appex/Info.plist
 13     <key>CFBundleIdentifier</key>
 14     <string>com.tencent.xin.watchapp.watchkitextension1</string>
...
 58             <key>WKAppBundleIdentifier</key>
 59             <string>com.tencent.xin.watchapp1</string>
```

# References
- [Theos简介](http://www.dechao.net/theos/)
- [iOS微信抢红包Tweak安装教程](http://www.swiftyper.com/ios-tweak-install-guide/)
- <https://www.reddit.com/r/jailbreakdevelopers/comments/3m2ynf/question_error_when_compiling_against_kirbytheos/>
- [软件破解过程详解（以Paw软件为例）](http://guochenglai.com/2016/06/16/paw-crack/)
- [逆向工程 - Reveal、IDA、Hopper、https抓包 等](http://www.cnblogs.com/dahe007/p/5546990.html)
- [Mac 版迅雷，免费使用高速通道，离线下载](http://www.jianshu.com/p/6d7e64920268)
