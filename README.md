# accountbook
### [ 개요 ]
+ 오픈뱅킹 API를 통해 자신의 모든 자산을 한눈에 볼 수 있고 소비패턴을 분석해주는 가계부 웹사이트

### [ 프로젝트 요약 ]
+ 사이트 명 : accountbook (가계부-한 눈에 보자)
+ 프로젝트 기간 : 2020.07.27 ~ 2020.09.11 (47일)
+ 개발 인원 : 5명
+ 구현 담당 기능 : 로그인/회원가입, 인증, 계좌 목록 조회, 거래 내역 조회

### [ 개발환경 ]
+ 언어 : JAVA 
+ 서버 : Apatch Tomcat 9.0
+ 개발툴 : Eclipse
+ Frond-end : HTML5, CSS3, JavaScript(jquery, ajax), Bootstrap
+ Back-end : Jsp&Servlet (Model 1)
+ DB : Oracle, JDBC
+ API : OpenBanking

### [ E-R Diagram ]

![ERD](https://user-images.githubusercontent.com/69949473/99375671-57d4b600-2907-11eb-9b00-bcb98b90c75b.png)

### [ 프로젝트 설명 ]

+ Index

![index](https://user-images.githubusercontent.com/69949473/99375755-6b801c80-2907-11eb-9061-6c1ab26ca15b.png)

> 가계부 웹사이트의 메인 페이지에서 Bootstrap Modal로 로그인 및 회원가입을 구현했습니다.
<br>

+ Auth

![auth](https://user-images.githubusercontent.com/69949473/99375801-76d34800-2907-11eb-8910-4faf92faba7d.png)

> 최초 로그인시 사용자인증 API를 통하여 Authorization Code를 획득(사용자의 동의를 받았다는 의미)한 이후에 이 code값을 이용하여 토큰을 발급받는 3-legged 방식을 진행합니다.

> Singleton 클래스 내부의 LazyHolder 클래스 정적 초기화 시 인스턴스를 생성하고 getInstance 메서드에서는 해당 클래스에서 생성된 인스턴스를 반환하는 형식으로 구현했습니다.

<br>

+ Calendar

![calendar](https://user-images.githubusercontent.com/69949473/99375867-894d8180-2907-11eb-993a-0a707efe5f7d.png)

> 월, 일 별 수입과 지출 금액을 계산하여 map을 사용하여 누적하고 합계를 보여줍니다.

> 첫 로딩시 오늘의 월, 일로 로딩되며 select box를 통해 해당 월의 Calendar에서의 수입, 지출금액을 확인할 수 있습니다. 또한 해당 날짜 클릭시 그날의 입출금 내역을 확인할 수 있습니다.

<br>

+ Account List

![list](https://user-images.githubusercontent.com/69949473/99376046-c3b71e80-2907-11eb-94cf-d6f6db24c35b.png)

> 등록계좌조회에 필요한 파라미터를  보낸 후 BufferedReader를 통해 읽고,
 Gson 라이브러리를 통해 JSON을 parsing합니다. 거래내역 조회시 필요한 
fintechUseNum을  ArrayList에 저장합니다.

> 사용자가 보유하고 있는 계좌목록을 보여주고 내역보기 클릭시 거내래역을 
보여주고, 등록된 계좌를 삭제할 수도 있습니다.

<br>

+ Transactional History

![history](https://user-images.githubusercontent.com/69949473/99376179-ed704580-2907-11eb-8cf5-f011ac590f48.png)

> 계좌목록 조회시 가져온 fintechUseNum들을 이용하여 각 계좌 클릭시 서버로 파라미터를 
보내고,  해당 거래내역을 받아옵니다. 날짜, 거래종류에 따라(식비, 교통비, 여가, 쇼핑, 기타) 
순서대로 현재 계좌의 잔액과 유동적으로 변화하는 입출금 내역을 확인할 수 있습니다.
마찬가지로  select box 통해 년, 월별 거래내역을 조회할 수 있습니다.
<br>


+ Analysis

![analysis](https://user-images.githubusercontent.com/69949473/99376258-0c6ed780-2908-11eb-9071-c84d2572cdbf.png)

> 식비, 교통비, 여가, 쇼핑, 기타 카테고리별 지출금액을 분석해줍니다.
이번달 목표 지출액 대비 progress와 최근 3개월 간의 지출습관을 볼 수 있습니다.
이를 통해 사용자는 자신이 언제 어느부분에서의 지출이 많은지 빠르게 파악이 가능하고
효율적인 소비 습관을 들일 수 있습니다.
<br>


+ Mypage

![mypage](https://user-images.githubusercontent.com/69949473/99376370-30321d80-2908-11eb-8d93-f2b2c353a7d0.png)

> 사용자의 정보와 연동계좌 목록을 확인할 수 있고, POST방식의 REST 방식을 통해
 계좌정보 변경 / 계좌 해지를 구현했습니다.
<br>
