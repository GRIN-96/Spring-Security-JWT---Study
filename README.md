
<img src="https://capsule-render.vercel.app/api?type=waving&color=auto&height=200&section=header&text=JWT&fontSize=90" />

<br/>
<br/>

# JWT ( JSON Web Token )

JWT는 유저를 인증하고 식별하기 위한 토큰(Token)기반 인증입니다.

토큰은 세션과 달리 서버가 아닌 클라이언트에 저장되기 때문에 메모리나 스토리지 등을 통해 세션을 관리했던 서버의 부담을 덜 수 있습니다.

데이터가 많이지면 토큰이 커질 수 있으며 한 번 발급된 이후 사용자의 정보를 바꾸어도 재발급하지 않는 이상 반영되지 안습니다.


<br/>
<br/>

## JWT 진행 순서

1. 클라이언트 사용자가 아이디, 패스워드를 통해 웹서비스를 인증합니다.

2. 서버에 서명된 JWT를 생성하여 클라이언트에 응답으로 돌려줍니다.

3. 클라이언트가 서버에 데이터를 추가적으로 요구할 때 JWT를 HTTP Header에 첨부합니다.

4. 서버에서 클라이언트로부터 온 JWT를 검증합니다.

<img src="https://www.okta.com/sites/default/files/styles/tinypng/public/media/image/2020-12/TokenBasedAuthentication.png?itok=zXMogDjG" />
<a href="https://www.okta.com/kr/identity-101/what-is-token-based-authentication/"> 이미지 출처 </a>

<br/>
<br/>


## JWT의 장점과 단점

- 장점
  1. 크기 : JSON 코드 언어로 생성된 토큰은 용량이 작기 때문에 두 엔티티 사이에서 매우 빠르게 전달됩니다.
  2. 용이성 : 거의 모든 곳에서 토큰이 생성될 수 있으며, 서버에서 토큰을 확인할 필요가 없습니다.
  3. 제어 : 엑세스 가능한 데이터, 권한 지속 시간, 로그인 시 가능한 작업을 지정할 수 있습니다.

- 단점
  1. 단일 키 : JWT는 단일 키를 이용합니다. 따라서 키가 유출될 시 시스템 전체가 위험에 노출됩니다.
  2. 복잡성 : 이 토큰은 이해하기가 쉽지 않습니다. 개발자가 암호 서명 알고리즘에 정통하지 않다면 자신도 모르게 시스템을 위험에 빠뜨릴 수 있습니다. 
  3. 제한 : 메세지를 모든 클라이언트에 푸시할 수 없고, 서버 측 클라이언트도 관리할 수 없습니다.

<br/>
<br/>


## 인증 토큰을 시도해야 하는 이유

- 임시 엑세스를 자주 허용하는 관리자의 경우 날짜, 시간 특별 이벤트에 따라 사용자 수의 변동 폭이 크면 액세스를 반복해서 허용 또는 취소하느라 쉽게 지칠 수 있습니다. 이때 토큰이 매우 유용합니다.

- 엑세스 세분화가 필요한 관리자의 경우 서버가 사용자 속성이 아닌 특정 문서 속성에 따라 액세스를 허용합니다. 하지만 비밀번호로는 정밀한 세분화가 어렵습니다.  예를들어 온라인 저널을 운영한다 가정했을 때, 모든 독자가 여러 문서가 아닌 한 문서 저널을 읽고 댓글을 달 수 있도록 만들려고 합니다. 이때 토큰을 사용하면 가능합니다.

- 주요 해킹 표적인 관리자의 경우, 정보유출 시 기업에게 심각한 피해를 입힐 수있는데요, 이를 비밀번호로만 보호하기엔 충분치 않습니다. 이때는 하드웨어가 큰 도움이 될 수 있습니다.

