# prepare_frontend_interview

## Computer Science

<b>프론트엔드 기술 면접을 위한 핸드북 만들기</b>

## 목차

- [프로세스와 스레드 🔥](#프로세스와-스레드)

  - 프로세스가 뭔가요?
  - 스레드가 뭔가요?
  - 프로세스와 스레드는 어떤 차이가 있나요?

- [싱글 스레드와 멀티 스레드 🔥](#싱글-스레드와-멀티-스레드)

  - 싱글 스레드 장점
  - 싱글 스레드 단점
  - 멀티 스레드 장점
  - 멀티 스레드 단점

- [HTTP 🔥](#HTTP)

  - HTTP란 뭔가요?
  - HTTP 프로토콜의 가장 큰 특징은 뭔가요?
  - URL은 뭔가요?
  - HTTP/1.1 과 HTTP/2.0의 차이는 뭔가요?
  - HTTPS는 HTTP랑 뭐가 다른가요?
  - 심화) 공개키 (비대칭키) 방식이 뭔가요?

- [쿠키 세션 🔥](#쿠키-세션)

  - 쿠키, 세션을 왜 쓰나요?
  - 쿠키가 뭔가요?
  - 세션이 뭔가요?
  - 쿠키와 세션의 차이는 어떤 점이 있을까요?

- [CORS 🔥](#CORS)

  - CORS가 뭔가요?
  - CORS를 겪고 직접 해결해 본 경험이 있으면 말해주세요

- [SaaS 🔥](#SaaS)

  - SaaS가 뭔가요?
  - 기타 비즈니스 유형​은 뭐가 있나요?

- [개발 방법론 🔥](#개발-방법론)

  - 폭포수 방법론이란 뭔가요?
  - 애자일 방법론이란 뭔가요?

- [Cache 🔥](#Cache)

- 캐시란 무엇인가요?

- [CI CD 🔥](#CI-CD)

  - CI CD란 뭔가요?

- [CDN 🔥](#CDN)

  - CDN이란 뭔가요?

- [테스트 🔥](#테스트)

  - 테스트란 무엇인가요?
  - 테스트의 예는 어떤 것들이 있나요?
  - 테스트는 왜 해야 하나요?
  - 유닛 테스트란 무엇인가요?
  - 통합 테스트란 무엇인가요?
  - E2E 테스트란 무엇인가요?

- [business logic 🔥](#business-logic)

  - business logic 이란 무엇인가요?

- [Snippet 🔥](#Snippet)

  - snippet 이란 무엇인가요?

- [웹팩 🔥](#웹팩)

  - 웹팩이란?
  - 모듈이란?
  - 모듈 번들링이란?
  - 웹팩이 등장한 이유 웹팩 사용 시에 이점
  - 바벨이란?
  - 웹팩의 주요 속성 4가지

- [타입과 인터페이스 🔥](#타입과-인터페이스)

  - 이 글을 보시는 분들께
  - 타입스크립트를 왜 쓰나요? (본인이 느낀점)
  - 타입과 인터페이스의 차이를 아나요? 🔥🔥🔥
  - 제네릭이란? 🔥🔥🔥

## 프로세스와 스레드

출처: [velog, 개발장님의 글 '프로세스와 스레드의 차이'](https://velog.io/@raejoonee/%ED%94%84%EB%A1%9C%EC%84%B8%EC%8A%A4%EC%99%80-%EC%8A%A4%EB%A0%88%EB%93%9C%EC%9D%98-%EC%B0%A8%EC%9D%B4)

### `프로세스가 뭔가요?`
- 실행되고 있는 컴퓨터 프로그램입니다.

### `스레드가 뭔가요?`
- 프로세스를 구성하는 더 작은 실행 단위입니다.

### `프로세스와 스레드는 어떤 차이가 있나요?`
- 스레드는 프로세스 안에 포함된 더 작은 실행 단위의 개념입니다.
- 프로세스는 메모리에 올라갈 때 운영체제로부터 독립적인 시스템 자원을 할당 받는 반면, 스레드는 프로세스 내부에서 다른 메모리 영역을 같은 프로세스 내 다른 스레드와 공유합니다.

## 싱글 스레드와 멀티 스레드

[출처: velog, 은진님의 글 '싱글스레드, 멀티스레드의 의미'](https://velog.io/@eunjin/OS-%EC%8B%B1%EA%B8%80%EC%8A%A4%EB%A0%88%EB%93%9C-%EB%A9%80%ED%8B%B0%EC%8A%A4%EB%A0%88%EB%93%9C%EC%9D%98-%EC%9D%98%EB%AF%B8)

<img src="https://media.vlpt.us/images/eunjin/post/c63d6950-7ae7-439a-9ee8-d6f145d6808a/Screen%20Shot%202021-01-17%20at%204.18.53%20PM.png" alt="싱글 스레드와 멀티 스레드">

### 싱글 스레드
- 하나의 프로세스에서 하나의 스레드를 실행합니다.

### 싱글 스레드의 장점
- 자원 접근에 대한 동기화를 신경쓰지 않아도 됩니다.
- 작업전환 작업을 요구하지 않습니다.

### 싱글 스레드의 단점
- 여러 개의 CPU를 활용하지 못합니다.

### 멀티 스레드
- 프로그램을 다수의 실행 단위로 나누어 실행합니다.

### 멀티 스레드의 장점
- 새로운 프로세스를 생성하는 것보다 기존 프로세스에서 스레드를 생성하는 것이 빠릅니다.
- 프로세스의 자원과 상태를 공유하여 효율적으로 운영이 가능합니다.
- 프로세스의 작업전환보다 스레드의 작업전환이 더 빠릅니다.

### 멀티 스레드의 단점
- 하나의 스레드만 실행중일 때는 실행시간이 오히려 지연될 수 있습니다.
- 멀티 스레딩을 위해 운영체제의 지원이 필요합니다.
- 스레드 스케쥴링을 신경써야 합니다.

## HTTP

[Link 🔥](https://joshua1988.github.io/web-development/http-part1/)

### `HTTP란 뭔가요?`
- HTTP는 HyperText Transfer Protocol의 약자로 데이터를 주고받기 위해 정의한 통신 프로토콜입니다.

### `HTTP 프로토콜의 가장 큰 특징은 뭔가요?`
- HTTP 프로토콜은 상태가 없는 (stateless) 프로토콜입니다. 이러한 특징 덕에 각각의 데이터 요청이 서로 독립적으로 관리됩니다.

### `URL은 뭔가요?`
- URL(Uniform Resource Locators)은 서버에 자원(resource)를 요청하기 위해 입력하는 영문 주소입니다.

URL의 구조는 다음과 같습니다

<img src="../cs_images/13.jpg" alt="URL 구조">

<br/>

### `HTTP/1.1 과 HTTP/2.0의 차이는 뭔가요?`
- HTTP/1.1은 기본적으로 커넥션 당 하나의 요청과 응답만 처리합니다.
- 따라서 요청할 리소스의 개수에 비례하여 응답 시간도 증가하는 단점이 있습니다.

<img width="400" src="../cs_images/14.jpg" alt="HTTP 1.1">

<br/>

- HTTP/2는 커넥션당 여러 개의 요청과 응답, 즉 다중 요청/응답이 가능합니다. 
- 따라서 HTTP/1.1에 비해 페이지 로드 속도가 약 50% 정도 빠

<img width="400" src="../cs_images/15.jpg" alt="HTTP 2.0">

<br/>

### `HTTPS는 HTTP랑 뭐가 다른가요?`

[Link 🔥](https://mangkyu.tistory.com/98)
[Youtube Link 🔥](https://www.youtube.com/watch?v=H6lpFRpyl14)

- HTTPS는 HTTP에 데이터 암호화가 추가된 프로토콜로 중간에 제 3자가 볼 수 없도록공개키 암호화를 지원하고 있습니다.

```
id: my_naver_id
pw: my_naver_pw
```

<br/>

### `심화) 공개키 (비대칭키) 방식이 뭔가요?`
- 공개키 방식은 암호화와 복호화에 사용하는 키가 서로 다른 암호화 방식을 말하며, 키가 노출되어도 비교적 안전하지만 속도가 느립니다.

## 쿠키 세션

[Link 🔥](https://github.com/junh0328/TIL/tree/master/Chore#%EC%BF%A0%ED%82%A4%EC%99%80-%EC%84%B8%EC%85%98)

### `쿠키, 세션을 왜 쓰나요?`
- HTTP는 연결이 끝나면 상태 정보가 유지되지 않는 특성(stateless)이 있다. 이렇게 유지되지 않는 로그인 정보를 유지하기 위해 쿠키와 세션을 사용합니다.

### `쿠키가 뭔가요?`
- 특정 웹 사이트를 방문 했을 때 만들어지는 정보를 담는 파일입니다.

#### `쿠키의 특징`
- 이름, 값, 만료일(저장 기간 설정), 경로 정보로 구성되어 있다.
- 클라이언트에 총 300개의 쿠키를 저장할 수 있다.
- 하나의 도메인 당 20개의 쿠키를 가질 수 있다
- 하나의 쿠키는 4KB(=4096byte)까지 저장 가능하다.

#### `쿠키의 동작 순서4`

<img width="400" src="../cs_images/4.jpg" alt="cookie">

1. 클라이언트가 페이지를 요청한다 (사용자가 웹사이트 접근) 웹 서버는 쿠키를 생성한다
2. 생성한 쿠키에 정보를 담아 HTTP 화면을 돌려줄 때, 같이 클라이언트에게 돌려준다
3. 넘겨 받은 쿠키는 클라이언트가 가지고 있다가(로컬 PC에 저장) 다시 서버에 요청할 때 요청과 함께 쿠키를 전송한다
4. 동일 사이트 재방문시 클라이언트의 PC에 해당 쿠키가 있는 경우, 요청 페이지와 함께 쿠키를 전송한다

<br/>

#### `사용 예시`
1. 방문했던 사이트에 다시 방문 하였을 때 아이디와 비밀번호 자동 입력
2. 팝업창을 통해 "오늘 이 창을 다시 보지 않기" 체크

<br/>

#### `쿠키의 약점`
1. 쿠키의 클라이언트(브라우저)단에 저장되므로 보안에 약합니다.

<br/>

### `세션이 뭔가요?`
- HTTP 세션이란 **클라이이언트가 웹서버에 연결된 순간부터 웹 브라우저를 닫아 서버와의 HTTP 통신을 끝낼 때 까지의 기간** 입니다.
- 
<br/>

#### `세션의 특징`
- 따로 용량의 제한이 없다 (서버의 능력에 따라 다를 수 있다)
- 서버에 세션 객체를 생성하며 각 클라이언트 마다 고유한 세션 ID 값을 부여한다
- 쿠키를 사용하여 세션 ID 값을 클라이언트에 보낸다
- 웹 브라우저가 종료되면 세션 쿠키는 삭제된다

<br/>

#### `세션의 동작 방식`

<img width="400" src="../cs_images/5.jpg" alt="세션">

1. 클라이언트 페이지가 요청한다
2. 서버가 클라이언트마다 개별의 세션 ID를 부여한다
3. 클라이언트는 요청할 때마다 세션 ID를 서버에 전달한다
4. 서버는 받은 세션 ID로 클라이언트 정보를 가져와 활용한다

<br/>

### `쿠키와 세션의 차이는 어떤 점이 있을까요?`
- 가장 큰 차이점은 사용자의 정보가 저장되는 위치입니다. 쿠키는 파일에 저장되며, 세션은 서버에 저장됩니다. 그러므로 세션이 보안 면에서 더 우수하며, 서버 요청시 속도가 비교적 느리고, 세션은 쿠키와 달리 브라우저가 종료되면 만료시간에 상관없이 삭제된다.

## CORS

[Link 🔥](https://velog.io/@young_pallete/CORS)

### `CORS가 뭔가요?`
- 자신이 속한 출처를 기준으로 다른 출처여도, 이미 예상되는 출처라면 브라우저가 응답 결과를 보내주는 겁니다.

<br/>

#### 왜 브라우저가 CORS 요청을 처리하나요?
- 브라우저는 거부해도 서버는 처리할 수 있기 때문에 안전을 위해 브라우저에서 COR를 처리합니다. 

<br/>

#### 실제 요청에서는 어떻게 처리하나요?
CORS는 다른 Origin에 대한 요청을 허용하는 정책입니다.

같은 Origin에서 http 통신을 하는 경우 알아서 cookie가 request header에 들어가지만, 교차 출처로 요청하는 상황에서는 그렇지 않습니다.

Origin이 다른 http 통신에서는 request header에 쿠키가 자동으로 들어가지 않기 때문에 서버에게 또는 클라이언트에게 내가 어떤 요청을 보내는 지 알려줄 필요가 있습니다.

```
프론트 > WithCredentials: true

서버 > Access-Control-Allow-Credentials: true
```

<br/>

### `CORS를 겪고 직접 해결해 본 경험이 있으면 말해주세요`
- 프로젝트때, 외부 API 서버에 요청했더니 CORS 정책을 위반해서 에러가 떴습니다. 그래서 프록시 서버를 사용해 우회하여 해결하였습니다.

## SaaS

[Link 🔥](https://www.redhat.com/ko/topics/cloud-computing/what-is-saas)

### `SaaS가 뭔가요?`
- 클라우드 인프라 위에 소프트웨어를 탑재해 제공하는 형태로 IT 인프라 자원뿐만 아니라 소프트웨어 및 업데이트, 버그 개선 등의 서비스를 업체가 도맡아 제공하는 것입니다.

### `기타 비즈니스 유형​은 뭐가 있나요?`

#### 1. PaaS(Platform as a Service)
- 개발자가 응용 프로그램을 작성할 수 있도록 플랫폼 및 환경을 제공하는 모델입니다.

#### 2. IaaS(Infrastructure as a Service)​
- 서비스 제공업체가 고객을 대신해 클라우드를 통해 인프라(실제 서버, 네트워크, 가상화, 스토리지)를 관리합니다.

## 개발 방법론

### `폭포수 방법론이란 뭔가요?`
- 앞의 단계를 완료한 후 순차적으로 진행하는 개발 프로세스이다.

<img width="500" src="../images/Waterfall_model.png" alt="폭포수 모델"/>

### `애자일 방법론이란 뭔가요?`

[Link 🔥](https://www.redhat.com/ko/devops/what-is-agile-methodology)

- 일정한 주기를 가지고 검토하며 개선하는 방식으로 진행하는 개발 프로세스입니다.

## Cache

[Link 10분 테코톡 -파피의 Caching 캐싱](https://www.youtube.com/watch?v=JBFT4KyEvoY&t=314s)

### `캐시란 무엇인가요?`

```
Caching == Cache + ing
```

### Cache
- Cache는 프랑스어로 `숨기다` 라는 뜻을 가지는 단어인 cacher 에서 파생된 단어로, 물건을 일시적으로 저장, 보관하기 위해 사용하는 곳입니다.

### 기술적 Cache
- 자주 필요한 데이터나 값의 복사본을 일시적으로 저장하기 위해 사용하는 곳입니다.

### Caching
- Cache를 사용하는 것

### Flow
- CPU는 데이터 처리를 위해 메모리와 끊임없이 데이터를 주고받는 구조
- 메모리가 CPU의 데이터 처리 속도를 쫓아가지 못함
- CPU가 메모리를 기다려야 하는 `병목현상` 발생

이 `병목현상` 을 완화하기 위해 CPU와 메인 메모리 사이에 크기는 작지만 속도가 빠른 **캐시 메모리**를 두고,

캐시 메모리에 향후 재사용할 가능성이 클 것으로 예상되는 데이터의 복사본을 저장해 둔 후 CPU가 요청하는 데이터를 바로바로 전달할 수 있도록 합니다

캐시 메모리의 용량을 크게 쓰거나, 아예 메인 메모리로 사용하면 되지 않냐고 물을 수 있는데, 캐시 메모리는 가격이 비싸다

메인 메모리는 DRAM, 캐시 메모리는 SRAM의 구조를 가지는데, SRAM이 셀당 트랜지스터의 개수도 많고 물리적으로 차지하는 면적 또한 훨씬 크다

<img width="500" src="https://s3.us-west-2.amazonaws.com/secure.notion-static.com/00adbdad-47b3-4ddd-a503-dddec358825c/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2022-02-14_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_12.47.52.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220325%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220325T140907Z&X-Amz-Expires=86400&X-Amz-Signature=f2fdc1914ab4f76593e30620515d8faa45c88667aec7161255224c98a3182f98&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA%25202022-02-14%2520%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE%252012.47.52.png%22&x-id=GetObject" alt="캐시 메모리"/>

<img width="500" src="https://s3.us-west-2.amazonaws.com/secure.notion-static.com/e9712134-5b79-48c6-b240-2d0d6a456ab5/%E1%84%86%E1%85%A6%E1%84%86%E1%85%A9%E1%84%85%E1%85%B5_%E1%84%80%E1%85%A8%E1%84%8E%E1%85%B3%E1%86%BC_%E1%84%80%E1%85%AE%E1%84%8C%E1%85%A9.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220325%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220325T141009Z&X-Amz-Expires=86400&X-Amz-Signature=a68f711398d6e8b1bd07222b8c1160153c72740cf2ea1ce80798a61dba1e167f&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22%25E1%2584%2586%25E1%2585%25A6%25E1%2584%2586%25E1%2585%25A9%25E1%2584%2585%25E1%2585%25B5%2520%25E1%2584%2580%25E1%2585%25A8%25E1%2584%258E%25E1%2585%25B3%25E1%2586%25BC%2520%25E1%2584%2580%25E1%2585%25AE%25E1%2584%258C%25E1%2585%25A9.png%22&x-id=GetObject" alt="메모리의 계층 구조"/>

[출처 - 테코톡 파피의 캐싱](https://www.youtube.com/watch?v=JBFT4KyEvoY&t=314s)

메모리의 계층 구조

- 상층 구조로 갈수록 빠르고, 비싸고, 작은 용량을 가집니다
- 또한 CPU와 가까이 위치하고 있습니다
- 캐시 메모리 들이 메인 메모리(RAM)보다 빠르지만, 비싸며, 면적 차지 또한 큰 것을 알 수 있습니다

이러한 메모리 계층 구조의 목적은 캐싱을 이용하여 빠르고 작은 메모리와 크고 느린 메모리의 조합을 이용하여 크고 빠른 메모리처럼 행동하도록 만들기 위함입니다.

재사용할 가능성이 클 것으로 예상되는 데이터의 복사본을 저장함으로써 캐싱을 할 수 있다고 했는데, 재사용할 가능성이 클 지는 어떻게 알 수 있을까? - 데이터 지역성의 원리를 이용합니다

### 데이터 지역성의 원리
- 데이터 접근이 시간적 혹은 공간적으로 가깝게 일어나는 것을 의미함
- 한 번 참조된 변수는 잠시 후에 또 참조될 가능성이 높다
- 어떤 데이터에 접근할 때, 그 데이터 근처에 있는 다른 데이터도 참조될 가능성이 높다

### 결론
캐싱: 캐시에 데이터나 계산된 결과 값의 복사본을 저장해 둠으로써 전체적인 처리 속도를 향상시킨다.

- 데이터에 직접적으로 접근하는 데 걸리는 시간이 오래 걸릴 때
- 필요한 값을 얻기 위해 계산하는 과정을 생략하고 싶을 때
- 반복적으로 동일한 결과를 돌려주는 경우(이미지나 썸네일 등)

캐싱은 복사본을 이용하는 것이다.(복사본과 원본이 달라지는 경우가 생길 수 있으니 일관성 유지에 유의)

## CI CD

[Link 🔥](https://www.redhat.com/ko/topics/devops/what-is-ci-cd)

### `CI CD란 뭔가요?`

<img src="https://www.redhat.com/cms/managed-files/styles/wysiwyg_full_width/s3/ci-cd-flow-desktop_edited_0.png?itok=TzgJwj6p" alt="CI/CD">

[출처: 레드헷 CI/CD](https://www.redhat.com/ko/topics/devops/what-is-ci-cd)

- CI/CD는 애플리케이션 개발 단계를 자동화하여 애플리케이션을 더욱 짧은 주기로 고객에게 제공하는 방법입니다.
- CI/CD의 기본 개념은 지속적인 통합, 지속적인 서비스 제공, 지속적인 배포입니다.

## CDN

### `CDN이란 뭔가요?`
- 지리적으로 분산된 여러 개의 서버로 웹 콘텐츠를 사용자와 가까운 곳에서 전송함으로써 전송 속도를 높인 것입니다. 

CDN 을 사용하는 대표적인 기업 - **[넷플릭스](https://www.bloter.net/newsView/blt202111060001), [슬랙](https://www.youtube.com/watch?v=oVaTiRl9-v0)**

CDN 서비스를 제공하는 대표적인 기업 - [**Amazon CloudFront**](https://aws.amazon.com/ko/cloudfront/)

## 테스트

### `테스트란 무엇인가요?`
- 어플리케이션이 요구사항에 맞게 동작하는지를 검증하는 행위입니다.

### `테스트의 예는 어떤 것들이 있나요?`
- DB에 데이터를 입력하는 API를 개발 > API 호출 > DB값 검증
- 디자인 시안에 맞게 HTML/CSS를 작성 > 브라우저에서 실제 렌더링된 결과를 확인
- 새로운 기능을 추가하기 위해 기존 모듈을 리팩토링 > 영향을 받는 다른 모듈의 실행 결과를 확인
- 버그를 수정하기 위해 기존 함수를 수정 > 버그가 수정 확인 & 영향을 받는 다른 모듈의 실행 결과를 확인
- 개발 환경에서 테스트된 어플리케이션을 리얼 환경에 배포 > 배포 과정에서 발생한 문제가 없는지 확인

### `테스트는 왜 해야 하나요?`
- 자동화된 테스트를 작성해두지 않으면, 어플리케이션이 복잡해질 수록 테스트 비용이 증가하고, 업무의 효율이 떨어지기 때문입니다.

### `유닛 테스트란 무엇인가요?`

**단위(Unit) 테스트**

- 모듈(함수/클래스) 단위의 테스트
- 작성 비용이 적게 들고 실행 속도가 빠름
- 실패했을 때 문제가 생긴 부분을 비교적 정확하게 파악할 수 있음

### `통합 테스트란 무엇인가요?`

**통합(Integration) 테스트**

- 주로 단위 테스트보다 큰 범위의 테스트를 의미
- 개별 모듈(함수/클래스)들이 연결되어 제대로 상호작용하는지를 테스트
- 단위 테스트에 비해 실패 시 문제가 생긴 부분을 정확히 파악하기가 어려움

### `E2E 테스트란 무엇인가요?`

**E2E(End to End) 테스트**

- 실제 사용자가 사용하는 것과 같은 조건에서 전체 시스템을 테스트
- 단위/통합 테스트에 비해 작성이 어렵고 실행 속도가 비교적 느림
- API 서버, DB 등의 외부 서비스들을 모두 사용하여 통합된 시스템을 테스트

## business logic

### `business logic 이란 무엇인가요?`
- 비즈니스 로직(도메인 로직/ 애플리케이션 로직)이란 프로그램의 핵심 로직으로 데이터의 생성·표시·저장·변경하는 부분을 말합니다.

[출처/ Su Bak님의 글 Business Logic이란?](https://medium.com/@su_bak/term-business-logic%EC%9D%B4%EB%9E%80-6d53c4782d73)

## Snippet

### `Snippet 이란 무엇인가요?`
- 스니펫(Snippet)은 재사용 가능한 소스 코드, 기계어, 텍스트의 작은 부분을 일컫는 프로그래밍 용어입니다.

VS Code 의 확장 프로그램 활용 - **Reactjs code snippets / Tabnine AI**

<img src="./cs_images/16.gif" alt="snippets"/>

## 웹팩

[Link 🔥](https://github.com/junh0328/CAPATIN_WEBPACK)

### `웹팩이란?`
- 웹팩이란 최신 프런트엔드 프레임워크에서 가장 많이 사용되는 모듈 번들러(Module Bundler)입니다.
- 모듈 번들러란 웹 애플리케이션을 구성하는 자원(HTML, CSS, Javscript, Images 등)을 모두 각각의 모듈로 보고 이를 조합해서 병합된 하나의 결과물을 만드는 도구를 의미합니다.

<img src="./cs_images/6.png" alt="bundle">

### `모듈이란?`
- 모듈이란 프로그래밍 관점에서 **특정 기능을 갖는 작은 코드 단위**를 의미합니다. 자바스크립트로 치면 아래와 같은 코드가 모듈입니다.

```js
// 📁 math.js

function sum(a, b) {
  return a + b;
}

function substract(a, b) {
  return a - b;
}

const PI = 3.14;

export { sum, substract, PI };
```

이 math.js 파일은 아래와 같이 3가지 기능을 갖고 있는 모듈입니다.

- 두 숫자의 합을 구하는 sum() 함수
- 두 숫자의 차를 구하는 substract() 함수
- 원주율 값을 갖는 PI 상수

이처럼 성격이 비슷한 기능들을 하나의 의미있는 파일로 관리하면 모듈이 됩니다.

웹팩에서 지칭하는 모듈이라는 개념은 위와 같이 자바스크립트 모듈에만 국한되지 않고 웹 애플리케이션을 구성하는 모든 자원을 의미합니다.

웹 애플리케이션을 제작하려면 HTML, CSS, Javascript, Images, Font 등 많은 파일들이 필요하죠. 이 파일 하나하나가 모두 모듈입니다.

### `모듈 번들링이란?`
- 아래 그림과 같이 웹 애플리케이션을 구성하는 몇십, 몇백개의 자원들을 하나의 파일로 병합 및 압축 해주는 동작을 모듈 번들링이라고 합니다.
- 파일들의 연관된 관계를 파악하여 파일들을 하나의 파일로 압축시켜주는 과정을 번들링 과정이라 합니다.

<img src="./cs_images/7.png" alt="모듈 번들링">

### `웹팩이 등장한 이유 웹팩 사용 시에 이점`
- 파일 단위의 자바스크립트 모듈 관리의 필요성을 충족합니다.
- 웹 개발 작업 자동화해주기에 편리합니다.
- 웹팩을 통해 모듈을 번들링하면, 로딩 속도가 빨라지고 성능이 높아집니다.

<details>
<summary>자세히 보기</summary>

<br/>

#### `파일 단위의 자바스크립트 모듈 관리의 필요성`

입문자 관점에서 고안된 자바스크립트는 아래와 같이 편리한 유효 범위를 갖고 있습니다.

```js
var window = 10;
console.log(window); // 10

function logText() {
  console.log(window); // 10
}
```

자바스크립트의 변수 유효 범위는 기본적으로 전역 범위를 갖습니다. 최대한 넓은 변수 범위를 갖기 때문에 어디에서도 접근하기가 편리하죠.

그런데 이러한 장점이 실제로 웹 애플리케이션을 개발할 때는 아래와 같은 문제점으로 변합니다.

```html
<!-- index.html -->
<html>
  <head>
    <!-- ... -->
  </head>
  <body>
    <!-- ... -->
    <script src="./app.js"></script>
    <script src="./main.js"></script>
    <script>
      getNum(); // ??
    </script>
  </body>
</html>
```

각각 다른 파일(app, main)에서 의도치 않게 같은 함수를 정의하고 호출했을 때, index.html에서는 어떤 함수를 불러오게 될까요?

```js
// app.js
var num = 10;
function getNum() {
  console.log(num);
}
```

```js
// main.js
var num = 20;
function getNum() {
  console.log(num);
}
```

결과는 가장 나중에 불러오게 되는 script 파일인 main.js에 선언된 값 20입니다.

app.js에서 선언한 num 변수는 main.js에서 다시 선언하고 20을 할당했기 때문이죠.

이러한 문제점은 실제로 복잡한 애플리케이션을 개발할 때 발생합니다.

변수의 이름을 모두 기억하지 않은 이상 변수를 중복 선언하거나 의도치 않은 값을 할당할 수 있죠.

이처럼 파일 단위로 변수를 관리하고 싶은 욕구, 자바스크립트 모듈화에 대한 욕구를 예전까진 AMD, Common.js와 같은 라이브러리로 풀어왔습니다.

#### `웹 개발 작업 자동화 도구`

이전부터 프런트엔드 개발 업무를 할 때 가장 많이 반복하는 작업은 텍스트 편집기에서 코드를 수정하고 저장한 뒤 브라우저에서 새로 고침을 누르는 것이었습니다. 그래야 화면에 변경된 내용을 볼 수 있었죠.

이외에도 웹 서비스를 개발하고 웹 서버에 배포할 때 아래와 같은 작업들을 해야 했습니다.

- HTML, CSS, JS 압축
- 이미지 압축
- CSS 전처리기 변환

이러한 일들을 자동화 해주는 도구들이 필요했습니다. 그래서 Grunt와 Gulp 같은 도구들이 등장했습니다.

#### `웹 애플리케이션의 빠른 로딩 속도와 높은 성능`

일반적으로 특정 웹 사이트를 접근할 때 5초 이내로 웹 사이트가 표시되지 않으면 대부분의 사용자들은 해당 사이트를 벗어나거나 집중력을 잃게 됩니다.

그래서 웹 사이트의 로딩 속도를 높이기 위해 많은 노력들이 있었습니다. 그 중 대표적인 노력이 브라우저에서 서버로 요청하는 파일 숫자를 줄이는 것입니다.

이를 위해 앞에서 살펴본 웹 태스크 매니저를 이용해 파일들을 압축하고 병합하는 작업들을 진행했습니다.

뿐만 아니라 초기 페이지 로딩 속도를 높이기 위해 나중에 필요한 자원들은 나중에 요청하는 레이지 로딩(Lazy Loading)이 등장했죠.

웹팩은 기본적으로 필요한 자원은 미리 로딩하는게 아니라 그 때 그 때 요청하자는 철학을 갖고 있습니다.

웹팩을 통해 모듈을 번들링하면, 해당 파일 들을 하나로 묶기 때문에 적은 HTTP 요청으로도 번들링 된 파일을 불러올 수 있습니다.

이러한 이유 때문에 우리는 웹팩을 사용합니다.

</details>

### `바벨이란?`
- 바벨은 자바스크립트에서 지원하는 최신 문법 (ES6, ES7, ES8, ES9, ...) 들을 최대한 많은 브라우저 환경에서 호환이 가능하도록 변환해주는(트랜스파일링해주는) 언어입니다.

#### `트랜스파일(transpile)`

<img src="./cs_images/8.png" alt="transpile">

#### `바벨 변환`

바벨을 사용하면 거대한 변화가 생기기 시작한 기점인 ES6 (ECMAScript 2015) 이후의 문법을 브라우저에서 범용적으로 사용되는 문법 단계로 변환해줄 수 있습니다.

```js
// Babel Input: ES2015 arrow function
[1, 2, 3].map((n) => n + 1);

// Babel Output: ES5 equivalent
[1, 2, 3].map(function (n) {
  return n + 1;
});
```

### `웹팩의 주요 속성 4가지`

1. entry
2. output
3. loader
4. plugin

#### `entry`

entry 속성은 웹팩에서 웹 자원을 변환하기 위해 필요한 최초 진입점이자 자바스크립트 파일 경로입니다.

`빌드를 할 대상 파일의 위치` 라고 볼 수 있습니다

```js
// webpack.config.js
module.exports = {
  entry: "./src/index.js",
};
```

<details>
<br/>

entry 속성에 지정된 파일에는 웹 애플리케이션의 전반적인 구조와 내용이 담겨져 있어야 합니다.

웹팩이 해당 파일을 가지고 웹 애플리케이션에서 사용되는 모듈들의 연관 관계를 이해하고 분석하기 때문에 애플리케이션을 동작시킬 수 있는 내용들이 담겨져 있어야 합니다.

```js
// index.js
import LoginView from "./LoginView.js";
import HomeView from "./HomeView.js";
import PostView from "./PostView.js";

function initApp() {
  LoginView.init();
  HomeView.init();
  PostView.init();
}

initApp();
```

싱글 페이지 애플리케이션으로 작성된 index.js를 예로 들어보겠습니다. 3개의 컴포넌트를 index.js에 불러와서 실행을 하고있는 구조입니다.

사용자의 로그인 화면, 로그인 후 진입하는 메인 화면, 그리고 게시글을 작성하는 화면 등 웹 서비스에 필요한 화면들이 모두 index.js 파일에서 불려져 사용되고 있기 때문에 웹팩을 실행하면 해당 파일들의 내용까지 해석하여 파일을 빌드해줄 것입니다.

<img src="./cs_images/9.png" alt="entry">

#### options

하지만 entry의 경우 엔트리 포인트가 1개가 될 수도 있지만 아래와 같이 여러 개가 될 수도 있습니다.

```
entry: {
  login: './src/LoginView.js',
  main: './src/MainView.js'
}
```

위와 같이 엔트리 포인트를 분리하는 경우는 싱글 페이지 애플리케이션이 아닌 특정 페이지로 진입했을 때 서버에서 해당 정보를 내려주는 형태의 멀티 페이지 애플리케이션에 적합합니다.

</details>

#### `output`

**output** 속성은 웹팩을 돌리고 난 결과물의 파일 경로를 의미합니다.

```js
// webpack.config.js
module.exports = {
  output: {
    filename: "bundle.js",
  },
};
```

앞에서 배운 entry 속성과는 다르게 객체 형태로 옵션들을 추가해야 합니다.

최소한 filename은 지정해줘야 하며 일반적으로 아래와 같이 path 속성을 함께 정의합니다.

```js
// webpack.config.js
var path = require("path");

module.exports = {
  output: {
    filename: "bundle.js",
    path: path.resolve(__dirname, "./dist"),
  },
};
```

- filename 속성은 웹팩으로 빌드(번들링)한 파일의 이름을 의미합니다.
- path 속성은 해당 파일의 경로를 의미합니다.
- path 속성에서 사용된 path.resolve() 코드는 인자로 넘어온 경로들을 조합하여 유효한 파일 경로를 만들어주는 Node.js API입니다.

**따라서 dist 라는 폴더 안에 있는 bundle.js라는 파일 이름으로 엔트리에 들어온 파일을 빌드(번들링)하여 결과물로 가져올 것입니다.**

<details>
<br/>

#### options

앞에서 살펴본 filename 속성에 여러 가지 옵션을 넣을 수 있습니다.

1. 결과 파일 이름에 entry 속성을 포함하는 옵션

```js
module.exports = {
  output: {
    filename: "[name].bundle.js",
  },
};
```

2. 결과 파일 이름에 웹팩 내부적으로 사용하는 모듈 ID를 포함하는 옵션

```js
module.exports = {
  output: {
    filename: "[id].bundle.js",
  },
};
```

3. [그 밖의 옵션](https://joshua1988.github.io/webpack-guide/concepts/output.html#output-%ED%8C%8C%EC%9D%BC-%EC%9D%B4%EB%A6%84-%EC%98%B5%EC%85%98)

</details>

#### `loader`

로더(Loader)는 웹팩이 웹 애플리케이션을 해석할 때 자바스크립트 파일이 아닌 웹 자원(HTML, CSS, Images, 폰트 등)들을 빌드 시에, 자바스크립트의 output(산출물) 파일에 포함될 수 있도록 도와주는 속성입니다.

```js
// webpack.config.js
module.exports = {
  module: {
    rules: [],
  },
};
```

엔트리나 아웃풋 속성과는 다르게 module라는 이름을 사용합니다.

#### `🔥 로더가 없는 경우`

로더는 앞서 말한대로 js 이외 형식의 파일들을 빌드할 때 추가하는 속성이라고 볼 수 있다.

만약 js 파일 내에 css 파일이 import 된 상황에서 loader가 없다면 어떻게 될까?

빌드가 제대로 되는 지 확인해보자

```js
📁 index.js

import "./base.css";
```

빌드를 한다면 다음과 같은 에러를 볼 수 있을 것이다.

<img src="./cs_images/10.png" alt="loader_error">

빌드 시에, 엔트리로 설정한 index.js 파일 내에 웹팩이 알아볼 수 없는 파일 형식자인 css가 포함되어서 이를 해석할 수 없다는 에러를 발생시켰다.

위와 같이 원래 목적인 js를 변환하는 것이 아니라면 loader를 통해 같이 빌드할 수 있는 여건을 만들어 줘야 한다

<details>
<summary>에시 코드 보기</summary>

<br/>

```js
📁 webpack.config.js

var path = require("path");

module.exports = {
  mode: "none", // production, development, none >> 배포 시에는 production으로 설정해야 한다
  entry: "./index.js",
  output: {
    filename: "bundle.js",
    path: path.resolve(__dirname, "dist"),
  },
  module: {
    rules: [
      {
        // 'test'는 확장자를 의미한다
        test: /\.css$/,
        // 'use'는 해당 파일들을 어떤 방향으로 로딩하는지 설정해주는 것이다

        // css-loader는 웹팩 안에 css 파일을 같이 번들링할 수 있도록 만드는 용도이다
        // style-loader는 해당 css를 html 파일 내에 인라인 코드로 실제 스타일에 적용하는 용도로 사용된다

        // 🔥 순서(오른쪽 to 왼쪽으로 적용) 또한 영향이 있으니, 먼저 적용되야 하는 로더를 오른쪽에 작성해야 한다
        use: ["style-loader", "css-loader"],
      },
      // 만든 바벨 로더 예시
      // {
      //   test: /\.js$/, test > 확장자
      //   use: ["babel-loader"], use > 사용할 라이브러리
      // },
    ],
  },
};
```

</details>

#### `plugin`

우리가 설정한 output인 bundle.js에 css 파일을 같이 번들링하는 것이 아닌 별도의 css 파일로 만들어주기 위해서는 플러그인을 사용할 필요가 있다

<img src="./cs_images/11.png" alt="plugin">

해당 적용이 완료된 후에 빌드를 하면 다음과 같이 번들링 시에 css 파일이 별도로 분리된 것을 볼 수 있다

<img src="./cs_images/12.png" alt="plugin_result">

플러그인(plugin)은 웹팩의 기본적인 동작에 추가적인 기능을 제공하는 속성입니다.

로더랑 비교하면 로더는 파일을 해석하고 변환하는 과정에 관여하는 반면, 플러그인은 해당 결과물의 형태를 바꾸는 역할을 한다고 보면 됩니다.

플러그인은 아래와 같이 선언합니다.

```js
// webpack.config.js
module.exports = {
  plugins: [],
};
```

플러그인의 배열에는 생성자 함수로 생성한 객체 인스턴스만 추가될 수 있습니다.

```js
// webpack.config.js
var webpack = require("webpack");
var HtmlWebpackPlugin = require("html-webpack-plugin");

module.exports = {
  plugins: [new HtmlWebpackPlugin(), new webpack.ProgressPlugin()],
};
```

- [Loader 보기 🔥](https://webpack.js.org/loaders/)
- [Plugin 보기 🔥](https://webpack.js.org/plugins/)

## 타입과 인터페이스

### 이 글을 보시는 분들께

어떤 면접을 보더라도 웹 프론트엔드를 공부하면서 타입스크립트 문법을 적용 중에 있다면 아래 3개의 질문은 필수로 질문을 해주시는 것 같습니다.

모든 분들의 가려운 부분을 정확히 긁어드릴 수는 없지만, 반드시 공부하시고 본인만의 답을 찾아 외우시면 도움이 될 것 같습니다.

### 타입스크립트를 왜 쓰나요? (본인이 느낀점) 🔥🔥🔥
- 정적 타입을 지원하기 때문에 컴파일 단계에서 오류를 포착할 수 있습니다. 이는 코드의 가독성을 높이고 예측가능하게 하며 디버깅을 쉽게 합니다.

<details>
<summary>이미지를 보며 차이점 알아보기</summary>

**타입이 없을 때**

<img src="./images/nonType.png" alt="타입이 없을 때" width="800">

**타입이 있을 때**

<img src="./images/Type.png" alt="타입이 없을 때" width="800">

</details>

### 타입과 인터페이스의 차이를 아나요?

[링크(참고문헌)](https://yceffort.kr/2021/03/typescript-interface-vs-type)

타입과 인터페이스는 모두 객체의 타입의 이름을 지정하는 방법들 중 하나이다

```ts
// interface
interface PeopleInterface {
  name: string;
  age: number;
}

const me1: PeopleInterface = {
  name: "yc",
  age: 34,
};

// type
type PeopleType = {
  name: string;
  age: number;
};

const me2: PeopleType = {
  name: "yc",
  age: 31,
};
```

하지만 일정 부분에 있어서 타입과 인터페이스는 차이점이 존재한다

1. 확장하는 방법

인터페이스는 `extends` 키워드를 사용하여 확장이 가능하고, 타입은 `&` 연산자를 통해 확장이 가능하다

```ts
// interface
interface PeopleInterface {
  name: string;
  age: number;
}

interface StudentInterface extends PeopleInterface {
  school: string;
}

// type
type PeopleType = {
  name: string;
  age: number;
};

type StudentType = PeopleType & {
  school: string;
};
```

2. 선언적 확장

인터페이스는 동일한 이름을 통해 재정의함으로써 선언적 확장이 가능하지만, 타입은 불가능하다

```ts
// interface
interface Window {
  title: string;
}

interface Window {
  ts: TypeScriptAPI;
}

// 같은 interface 명으로 Window를 다시 만든다면, 자동으로 확장이 된다.

const src = 'const a = "Hello World"';
window.ts.transpileModule(src, {});

// type
type Window = {
  title: string;
};

type Window = {
  ts: TypeScriptAPI;
};

// Error: Duplicate identifier 'Window'.
// 타입은 안된다.
```

여러 타입 혹은 인터페이스를 병합할 때 (`&` or `extends`), 인터페이스는 속성간의 충돌을 해결하기 위해 단순한 객체 타입을 만든다.

인터페이스는 오로지 객체의 타입을 만들기 위한 것이기 때문이다.

타입은 재귀적으로 순회하면서 속성을 병합하는데, 이 경우에 일부 `never`가 나오면서 제대로 머지되지 않을 수 있다. 인터페이스와는 다르게 타입에는 원시 타입이 올 수도 있으므로, 충돌이 나서 병합이 안되는 경우가 발생한다.

객체에만 쓰는 용도라면 interface를 사용하는 것이 좋을 것이다.

`핵심 키워드 🔥🔥🔥`

인터페이스는 자신의 이름을 중복 선언하여 `extends` 키워드를 사용하지 않더라도 확장이 가능하지만,

타입의 경우 중복 선언을 통해 확장할 수 없다. (& 연산자를 사용하여 확장해야 한다)

### 프로젝트 진행 시에 어떤 상황에서 타입을 쓰고 어떤 상황에서 인터페이스를 썼나요?

### 제네릭이란? 🔥🔥🔥
- **제네릭은 클래스, 함수, 인터페이스 등을 다양한 타입으로 재사용가능하게 해주는 문법**입니다

```ts
function getSize(arr: number[] | string[] | boolean[]): number {
  return arr.length;
}

const arr = [1, 2, 3];

getSize(arr); // 3

const arr2 = ["a", "b", "c"];

getSize(arr2); // 3

const arr3 = [true, false, true];
getSize(arr3); // 3
```

위와 같이 한가지 함수에서 다양한 타입의 데이터를 받아줘야한다고 가정할 때 올바른 타입을 지정하기 위해서는 타입을 확장시켜줘야 합니다.

이런 상황에서 제네릭을 사용하여 함수의 매개변수에 대한 타입 `<T>`를 명시해줌으로써 다양한 타입에 대응하는 함수를 만들어줄 수 있습니다.

```ts
function getSize<T>(arr: T[]): number {
  return arr.length;
}

const arr = [1, 2, 3];

getSize<number>(arr); // 3

const arr2 = ["a", "b", "c"];

getSize<string>(arr2); // 3
```

`한 줄 요약`

제네릭은 클래스, 함수, 인터페이스 등에서 한 가지 함수가 다양한 타입의 데이터를 받아줘야할 때 올바른 타입을 지정하기 위해 사용하는 재사용 가능한 확장 문법입니다.

## [내가 뽑은 1장 스터디 핵심질문 5개 🔥🔥]
(불 이모지가 붙은 질문은 공통질문입니다.)

1. HTTP와 HTTPS란 무엇이고 차이는 무엇인가요?🔥
- HTTP란 데이터를 주고받기 위해 정의된 프로토콜로, 웹에서는 브라우저와 서버 간에 데이터를 주고받기 위한 프로토콜 방식으로 사용하고 있습니다. 이는 상태가 없는 프로토콜로 데이터를 주고 받기 위한 각각의 데이터 요청이 서로 독립적으로 관리가 되어 서버 성능 상의 이점이 생깁니다. HTTPS는 HTTP에 데이터 암호화가 추가된 프로토콜로, 제3자가 정보를 볼 수 없도록 비대칭키 암호화를 지원하고 있습니다. 비대칭키 암호화 방식은 암호화와 복호화에 사용하는 키가 서로 다른 암호화 방식을 말하며, 키가 노출되어도 비교적 안전하지만 속도가 느립니다.

2. 프로세스와 스레드란?
- 우선 프로그램이란, 파일이 저장 장치에 저장되어 있지만 아직 독립적인 메모리공간에 올라가 있지 않아 운영체제 실행 전인 정적인 상태를 말합니다. 프로그램을 실행한 동적인 상태를 프로세스라고 하며, 프로세스와는 다른 더 작은 실행 단위 개념이 바로 스레드입니다. 스레드는 프로세스와 다르게 스레드 간 메모리를 공유하며 작동합니다. 즉 스레드는 프로세스의 코드에 정의된 절차에 따라 실행되는 특정한 수행 경로입니다.
  
3. 쿠키와 세션의 차이는 어떤 점이 있을까요?🔥
- 쿠키는 사용자가 어떠한 웹 사이트를 방문할 경우, 그 사이트의 서버에서 사용자의 정보를 컴퓨터에 저장하는 파일입니다. 따라서 서버가 사용자를 식별할 수 있게 합니다. 세션은 사용자가 브라우저에 접속하여 서버와 접속이 종료하기 전의 상태를 의미합니다. 쿠키는 서버의 자원을 전혀 사용하지 않고 파일에 저장되며, 세션은 서버에 저장됩니다. 그렇기 때문에 세션이 보안 면에서 더 유리합니다. 쿠키는 브라우저를 종료해도 계속해서 정보가 남아 있을 수 있고, 세션은 브라우저가 종료되면 만료시간에 상관없이 삭제됩니다. 쿠키는 서버 요청시 속도가 빠르고, 세션은 정보가 서버에 있기에 비교적 느립니다.

4. 캐시란 무엇인가요?
- 캐시란 미리 결과를 저장하고 나중에 요청이 오면 그 요청에 대해서 DB 또는 API를 참조하지 않고 Cache를 접근하여 요청을 처리하는 것입니다. 캐시에는 반복적으로 요구되는 데이터를 저장합니다. 이렇게 데이터의 전송량을 줄여 빠른 서비스, 즉 웹페이지의 빠른 렌더링을 돕습니다.

5. 타입스크립트를 왜 쓰나요?🔥
- 타입스크립트를 사용하는 가장 큰 이유는 정적 타이핑을 지원한다는 것입니다. 자바스크립트의 특징인 동적 타이핑은 자동으로 해석되기 때문에 의도에 따라 전달하는 데이터의 타입이 불분명해질 수 있습니다. 그러므로 타입을 지정함으로써, 코드에 목적을 명시하고, 버그를 사전에 제거합니다.

## [스터디원이 뽑은 핵심질문 🔥🔥]

1. 웹팩이란?
- 웹팩이란 최신 프런트엔드 프레임워크에서 가장 많이 사용되는 모듈 번들러입니다. 웹 애플리케이션을 구성하는 자원(HTML, CSS, Javscript, Images 등)을 모두 각각의 모듈로 보고 이를 조합해서 병합된 하나의 결과물을 만드는 도구를 의미합니다.

2. CORS란?
- CORS는 Cross Origin Resource Sharing의 약자로, 현재 ① 자신이 속한 출처(Origin)를 기준으로 ② 다른 출처(Origin)에 API를 요청하게 되면 브라우저에서 이 요청으로 넘어오는 경과가 안전한지 판단하게 되는데, 응답을 보내는 출처가 ① 자신이 속한 출처가 아닌, ② 다른 출처여도 서로 예상되는 출처라면 요청에 대해 허용해주는 응답 헤더를 보내, 브라우저가 응답 결과를 보여줍니다.


