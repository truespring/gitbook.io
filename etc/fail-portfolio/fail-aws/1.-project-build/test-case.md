---
description: test case 부재로 인한 build fail
---

# Test Case

build 를 할 당시의 project 상황은 intellij 에서 new project 를 통해 spring initialize, kotlin, java 11 로 생성하였고, AppController.kt 파일을 생성하여 localhost:8080/ 로 이동하였을 때 'Hello World!' 를 출력할 수 있도록 추가하고 완료한 상태였다.

build 를 실행하자 test case 에 관한 에러를 발생하며 제대로 된 build 가 되지 않았다.

우선 test 디렉토리 하위에 존재하는 class 파일을 제거하고 build 를 하였더니 정상적으로 build 를 완료할 수 있었다.

