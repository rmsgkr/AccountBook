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

> 밀키트 쇼핑몰 웹사이트의 메인화면으로 공지사항/이벤트 슬라이드, 베스트 상품 추천, 타임세일과 각종 정보를 보여줍니다.
<br>

+ Auth

![auth](https://user-images.githubusercontent.com/69949473/99375801-76d34800-2907-11eb-8910-4faf92faba7d.png)

> 상품명 검색을 통해 상품을 조회할 수 있는 검색기능과 등록되어있는 상품 전체 목록을 볼 수 있습니다. 상품 목록은 판매인기순, 낮은가격순, 높은가격순으로 정렬하여 볼 수 있고 찜하기, 장바구니담기, 상세보기가 가능합니다. 상품 상세 페이지에서 수량을 입력할 수 있고 장바구니에 담을 수 있습니다. 해당 제품의 구매가 완료된 사람은 리뷰를 등록할 수도 있게 구현하였습니다. 
<br>

+ Calendar

![calendar](https://user-images.githubusercontent.com/69949473/99375867-894d8180-2907-11eb-993a-0a707efe5f7d.png)

> sql을 통해 각 상품별 수량과 가격이 합산되어 update되고, 장바구니에 없는 상품은 새롭게 insert됩니다. Bootstrap Modal로 개별 삭제가 가능하도록 구현했고 주문하기 버튼을 누르면 장바구니에 존재하는 상품들이 주문페이지로 넘어가게 됩니다. 
주문이 완료되면 장바구니는 전체 삭제되도록 했습니다. 
<br>

+ Account List

![list](https://user-images.githubusercontent.com/69949473/99376046-c3b71e80-2907-11eb-94cf-d6f6db24c35b.png)

> 주문하는 클라이언트의 정보와 총금액이 넘어옵니다. 
쿠폰과 적립금의 중복사용을 막았고 사용가능한 쿠폰과 적립금을 보여줍니다.
이 과정에서 쿠폰/적립금 사용여부를 체크하여 환불시에 적용할 수 있도록 했습니다.
결제하기 버튼을 누르면 결제페이지로 넘어가게 됩니다.
<br>

+ Transactional History

![history](https://user-images.githubusercontent.com/69949473/99376179-ed704580-2907-11eb-8cf5-f011ac590f48.png)

> i'mport API를 이용하여 결제창을 띄웁니다. 쿠폰/적립금, 배송비가 적용된 최종 금액으로 결제되며 여러가지 결제방식을 제공합니다. 
<br>


+ Analysis

![analysis](https://user-images.githubusercontent.com/69949473/99376258-0c6ed780-2908-11eb-9071-c84d2572cdbf.png)

> i'mport API를 이용하여 결제창을 띄웁니다. 쿠폰/적립금, 배송비가 적용된 최종 금액으로 결제되며 여러가지 결제방식을 제공합니다. 
<br>


+ Mypage

![mypage](https://user-images.githubusercontent.com/69949473/99376370-30321d80-2908-11eb-8d93-f2b2c353a7d0.png)

> i'mport API를 이용하여 결제창을 띄웁니다. 쿠폰/적립금, 배송비가 적용된 최종 금액으로 결제되며 여러가지 결제방식을 제공합니다. 
<br>
