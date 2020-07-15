# 问题1 Error running Gradle:ProcessException: Process "/root/workspace/android/gradlew" exited abnormally:Starting a Gradle Daemon
- 日期：07/15/2020
- 简述：flutter 构建流水线报错
- 详细描述 如下：

```
+ flutter build apk --debug -t lib/main_dev.dart
Initializing gradle...                                             65.1s
Resolving dependencies...                                       
* Error running Gradle:
ProcessException: Process "/root/workspace/android/gradlew" exited abnormally:
Starting a Gradle Daemon (subsequent builds will be faster）

```
- 解决方案:将 gradle-wrapper.properties中的版本改成5.1.1
```
 #Fri Jun 23 08:50:38 CEST 2017
distributionBase=GRADLE_USER_HOME
distributionPath=wrapper/dists
zipStoreBase=GRADLE_USER_HOME
zipStorePath=wrapper/dists
distributionUrl=https\://services.gradle.org/distributions/gradle-5.5.1-all.zip

```



