---
description: 너무 느린 빌드 속도
---

# 빌드 속도

## Build 속도

aws ubuntu에 kotlin 프로젝트를 git에서 clone 하여 폴더를 복제하였다.

```text
$ sudo ./gredlew clean build
```

해당 명령어를 통하여 프로젝트 빌드를 시작하였는데 너무 오래 걸렸다. 이를 해결하기 위해 블로그를 찾아 다음과 같은 명령어를 찾을 수 있었다.

```text
# properties 파일을 새로 만듦
$ vi ~/.gradle/gradle.properties
```

> `org.gradle.daemon=true`
>
> `org.gradle.parallel=true`
>
> `org.gradle.workers.max=3`
>
> `org.gradle.configureondemand=true`
>
> `org.gradle.jvmargs=-Xms128m -Xmx256m`

이후 다시 빌드를 통하여 kotlin 프로젝트를 빌드 하였으나, 다음 문제가 발생했다.



