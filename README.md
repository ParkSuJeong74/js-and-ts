# js-and-ts

코어 JS와 브라우저 등을 학습하고 TS까지 정리하기 위해 작성합니다.

## JavaScript

- 공부 대상 : [JS 튜토리얼](https://ko.javascript.info/)

### 1. 코어 자바스크립트

JS와 호스트 환경 소개

#### a. 소개

<details>
  <summary>자바스크립트란?</summary>
  자바스크립트는 웹페이지에 생동감을 불어넣기 위해 만들어진 프로그래밍 언어이다. 자바스크립트로 작성한 프로그램은 `스크립트Script`라고 부른다. html 안에 작성하면 웹페이지를 불러올 때 스크립트가 자동으로 실행된다. 컴파일 없이도 작성할 수 있고 실행도 가능하다.
서버에서도 실행할 수 있다.

처음의 이름은 LiveScript이다. 자바의 인기로 이름을 차용하면서 자바스크립트가 되었지만 고유한 명세인 ECMAScript를 갖춘 독립적인 언어가 되었다.

`자바스크립트 엔진`이라는 특별한 프로그램이 들어있는 모든 디바이스에서 동작한다. 브라우저엔 `자바스크립트 가상 머신`이라는 엔진이 내장되어 있다. chrome과 opera에서 쓰이는 `V8`, firefox에서 쓰이는 `spiderMonkey`가 있다.

엔진은 스크립트를 `파싱`하고 `컴파일`한 후 코드를 `실행`시키는 과정으로 동작한다. 프로세스 각 단계마다 `최적화`를 진행하고 컴파일이 끝나고 실행 중인 코드를 감시하며 데이터를 분석하고 또다시 최적화하는 과정으로 스크립트 실행 속도를 더 높인다.

모던 JS는 메모리나 CPU 같은 저수준 영역의 조작을 허용하지 않기 때문에 안전하다. 실행 환경에 따라 능력치가 다른데, `Node.js` 환경에선 임의의 파일을 읽거나 쓰고 네트워크 요청을 수행하는 함수를 지원한다. 

브라우저 환경에서는 웹페이지 조작, 클라이언트와 서버의 상호작용에 관한 모든 일을 할 수 있다.

- html 혹은 스타일 수정
- 사용자의 행동(마우스, 키보드 등)에 반응
- 네트워크로 원격 서버에 요청을 보내기
- 쿠키를 가져오거나 설정
- 사용자에게 질문을 던지거나 보여주기
- 로컬 스토리지에 데이터 저장

브라우저에서 제약사항도 있다. 악성 웹페이지가 개인 정보에 접근하거나 데이터를 손상하는 것을 막기 위해서이다.

- 웹페이지 내 스크립트는 디스크에 저장된 파일을 제어할때 제약이 있다. OS가 지원하는 기능을 브라우저가 직접 못하게 막혀있기 때문이다. 모던 브라우저를 쓰더라도 제한이 막혀있고 `<input>` 태그를 통해서만 파일 접근을 허용한다. 카메라나 마이크 같은 디바이스와의 상호작용은 명시적인 허가가 필요하다. 사용자 모르게 국가안보국NSA에 전송하는건 불가능하다.
- 브라우저 내 탭과 창은 서로 정보를 알 수 없다. 한 창에서 다른 창을 열 때는 예외가 적용되지만 도메인이나 프로토콜, 포트가 다르면 페이지에 접근할 수는 없다. `동일 출처 정책Same Origin Policy`라고 부르는데 이 정책을 피하려면 두 페이지는 데이터 교환에 동의해야하고 동의와 관련된 특수한 JS 코드를 포함하고 있어야한다.
- 페이지를 생성한 서버와 정보를 주고 받을 수 있지만 타 사이트나 도메인에서 데이터를 받기 위해서는 명확히 승인을 해줘야한다(http 헤더를 이용)

서버는 이러한 제약이 없고 다만 모던 브라우저에선 추가 권한 허가를 요청하는 플러그인이나 익스텐션 설치가 허용된다.

JS의 강점은 html/css와 완전히 통합할 수 있다는 점, 간단한 일을 간단하게 처리할 수 있으며 모든 주요 브라우저에서 지원하고 기본 언어로 사용된다는 점이다. 브라우저 인터페이스를 만들 때 가장 널리 사용되고 서버나 모바일 앱에서도 사용된다.

JS 문법으로 요구를 충족하지 못하는 경우, 브라우저에서 실행되기 전에 JS로 `트랜스파일transpile`할 수 있는 언어들이 등장했다. JS가 아닌 언어로 작성된 코드를 보이지 않는 곳에서 JS로 변환해준다. 대표적으로 `TypeScript`가 있다. 개발을 단순화하고 복잡한 시스템을 지원하려는 목적으로 `자료형의 명시화`에 집중해 만든 언어이다.
</details>

> 알게된 내용 정리
>
> 엔진은 계속해서 최적화 한다.
> 현재 내가 개발할때 사용하는 JS 가상 머신이 V8이다. (크롬)
> 보안을 위한 제약사항 중 동일 출처 정책Same Origin Policy은 하나의 창에서 다른 창을 열때 도메인과 프로토콜, 포트가 다르면 데이터 교환에 제약을 거는 것이다.
> typescript로 작성된 코드는 브라우저에서 JS로 트랜스파일한다.
