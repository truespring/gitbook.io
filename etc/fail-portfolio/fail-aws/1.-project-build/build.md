---
description: 빌드 속도를 개선하다.
---

# Build

간단하게 'Hello World!' 를 띄울 수 있게 준비한 다음 ec2 에  git clone 을 하였고 빌드를 실행하였다.

```text
# git 에서 프로젝트 가져옴
$ git clone [git address]

# project 경로 이동
$ cd [project]

# project build
$ sudo ./gradlew clean build
```

30분이 지나도록 build 가 되지 않았고 인스턴스를 껏다 켯다를 반복하였으나, build 가 완료되는 일은 없었다.

구글링을 하여 gradle build 속도를 개선할 수 있는 방법을 찾을 수 있었다.

```text
$ vi gradle/gradle.properties

org.gradle.daemon=true
org.gradle.parallel=true
org.gradle.workers.max=3
org.gradle.configureondemand=true
org.gradle.jvmargs=-Xms128m -Xmx256m
```

properties 를 추가하여 빌드 속도를 개선하였고, ec2 에 정상적으로 build 를 하게 되었나 싶었지만, 다음 문제가 발생하며 build fail 이 발생하게 된다.

