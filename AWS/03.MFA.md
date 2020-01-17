### AWS Authentication
#### AWS - 보안설정 - 2단계 인증(Multi facotr 인증)

회원가입시 등록한 카드의 유효여부 확인을 위해 USE $1.00가 결제됨.

AWS에 가입 후 서비스를 이용할 수 있는 Management Console에 접근할 때,<br>
서버 관리 보안을 위해 로그인 비밀번호 수준을 높임과 동시에<br>
2단계 인증으로 보안 설정을 높이면 AWS 서비스와 리소스에 대한 액세스를 안전하게 관리할 수 있다.

`상단 계정 클릭 - 내 보안 자격 증명 - Indentity and Access Management(IAM)`<br>
또는 `AWS Management Console - 전체 서비스 - 보안, 자격 증명 및 규정 군수 - IAM`에서 대시보드를 확인하면

**루트 계정에서 MFA 활성화 / 멀티 팩터 인증(MFA)** 가 있다. (Activate MFA on your root account)<br>
MFA(Multi-Factor Authentication 멀티 팩터 인증)을 활성화 함.<br>
로그인 비밀번호와 모바일 디바이스를 이용한 2단계 인증 로그인하는 것.<br>

* MFA 설정 
  - MFA 인증 클릭 - 가상 MFA 디바이스(A virtual MFA device) 선택 - Next
  - '호환 어플리캐이션 목록을 참조'를 보면, 2단계 인증으로 사용할 수 있는 앱들의 리스트를 볼 수 있다.<br>
    보통 구글 OTP앱을 많이 사용함. 안드로이드, 아이폰에서 사용할 수 있는 모바일 앱.
  - Google OTP 어플로 2단계 인증을 통해 Google 계정에 로그인할 때 보안을 강화한다.

    * Google OTP 사용
      1. 모바일 App Store 에서 Google Authenticator 어플리케이션을 설치<br>
      2. 모바일 앱을 실행하여, MFA 설정 중인 웹 브라우저에 나타난 QR 코드 스캔 혹은 문자를 입력한다.<br>
      3. Authentication Code 1, 2에 어플에 나타나는 6자리 코드를 입력하여 가상 MFA 디바이스 설정을 완료한다.<br>
      4. 대시보드 reload 하여 확인하면 경고창이 떴던 Activate MFA on your root account 목록이 활성화되어있다.

AWS 로그아웃 하여 2단계 보안 인증 설정을 확인한다.<br>
이메일 주소, 비밀번호를 입력하면 MFA 코드를 제출해야하는 화면이 나온다.<br>
처음 2단계 인증을 설정할 때와 같이, 모바일 앱 구글 OTP 에서 제공해주는 6자리를 입력하면 로그인에 성공한다.

휴대폰을 잃어버리거나 하는 트러블이 생겼다면 고객센터를 통해 MFA 문제를 해결할 수 있다.<br>
직원과의 전화통화를 통하게 됨. 잘 관리해야한다.

ref 생활코딩
