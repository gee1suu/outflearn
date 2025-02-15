# IT 강의 플랫폼 '아웃풋런'
![메인화면](https://user-images.githubusercontent.com/80879666/208001687-915c4a04-5939-45ac-947b-04758861d5ca.png)
## 주제
![주제](https://user-images.githubusercontent.com/80879666/208002602-27d84a8f-7669-43f6-83a6-8b78abc59049.png)
사용자들이 IT에 관해 자유롭게 소통할 수 있는 **커뮤니티 기능**과 원하는 강의를 구매하고 판매할 수 있는 **스토어 기능**을 모두 사용할 수 있는 IT 강의 플랫폼 웹사이트
## 메뉴 구성
+ **공통**: 메인, 사용자 조회, 전체 채팅방, 1:1 채팅방
+ **회원 관리**: 회원가입, 로그인, 아이디 찾기, 비밀번호 재설정, 회원정보 수정, 비밀번호 변경, 회원탈퇴, 고객센터
+ **커뮤니티**: 자유주제 게시판, 질문 게시판, 로드맵 게시판
+ **강의(스토어)**: 온라인 강의, 오프라인 강의, 장바구니/결제, 실시간 질문, 구매내역 조회, 찜목록 조회, 수강 강의/로드맵 조회
+ **강의자**: 메인(대시보드), 강의자 신청, 강의 새소식 게시판, 매출 조회, 강의/로드맵 관리
+ **관리자**: 메인(대시보드), 고객센터 답변게시판, 가입자수/매출 통계, 전체 메일 발송, 공지사항/FAQ 게시판, 강의자 가입 승인, 신고글 조회, 고객센터 채팅
## 개발 환경
+ **프로젝트 기간**: 2022.11.15 ~ 2022.12.15
+ **개발 웹서버**: Apache Tomcat 9.0
+ **개발 프레임워크**: Spring 4.3.16, MyBatis, Maven
+ **개발 툴**: Eclipse IDE, IntelliJ IDEA, Oracle SQL Developer
+ **사용 언어**: Java(JDK 1.8), SQL, JSP & Servlet, HTML/CSS, JavaScript, Ajax
+ **API**: 카카오맵, 구글 로그인, 네이버 로그인, I'mport, 카카오페이, 트위터 공유, Summernote, Websocket, SockJS, Java Mail, WebRTC, PeerJS, POI
## 역할 분담
![역할분담](https://user-images.githubusercontent.com/80879666/208002878-cd43ce00-ffdb-49ad-9b5b-8f8ce6df3545.png)
## DB 설계
![DB설계](https://user-images.githubusercontent.com/80879666/208005218-52092dbb-1d63-4fc7-aad3-bee69a31b82c.png)
<details>
<summary>

### 사용자

</summary>

![사용자](https://user-images.githubusercontent.com/80879666/208005628-fb4595e2-ab27-44ae-92e5-d51b08f81778.PNG)
+ **유저**: 아이디, 등급, 이름, 생년월일, 비밀번호, 가입일, 포인트, 소셜로그인타입, 유저소개글
+ **등급**: 등급

</details>
<details>
<summary>

### 강의

</summary>

![강의](https://user-images.githubusercontent.com/80879666/208008151-ca45f140-5d06-4da0-8751-1920a2bdb2e4.PNG)
+ **강의**: 강의번호, 아이디, 카테고리이름, 강의제목, 강의작성자, 강의URL, 강의기한, 강의수준, 강의상세내용, 강의요약내용, 강의할인률, 강의할인기한, 강의가격, 강의등록일, 강의커버이미지, 섹션명, 온오프여부, 수강생수
+ **수업(온라인)**: 수업번호, 강의번호, 카테고리이름, 섹션번호, 수업명, 영상파일, 무료공개여부, 자료파일저장이름, 자료파일원본이름
+ **시간표(오프라인)**: 시간표번호, 강의번호, 강의실주소, 최대인원수, 강의시작시간, 강의종료시간, 강의지번주소
+ **강의카테고리**: 카테고리이름, 카테고리번호
+ **강의찜**: 찜번호, 강의번호, 아이디
+ **강의새소식**: 게시판번호, 강의번호, 강의작성자, 새소식제목, 새소식내용, 작성일자
+ **수강후기**: 게시판번호, 강의번호, 아이디, 평점, 후기내용, 작성일자
+ **수강후기_댓글**: 댓글번호, 게시판번호, 강의번호, 강의작성자, 댓글내용, 댓글작성일자
+ **강의자신청**: 아이디, 카테고리이름, 이름, 연락처, 소개글, 소개링크, 신청현황, 신청일

</details>
<details>
<summary>

### 게시판

</summary>

![게시판](https://user-images.githubusercontent.com/80879666/208005947-5cff25bf-2874-4b80-9792-e7c47a4406a9.PNG)
+ **자유게시판**: 글번호, 아이디, 등급, 글제목, 글내용, 작성일자, 조회수, 좋아요, 파일, 코멘트수
+ **자유게시판_댓글**: 댓글번호, 글번호, 아이디, 등급, 댓글내용, 댓글작성일자
+ **자유게시판_대댓글**: 대댓글번호, 댓글번호, 아이디, 등급, 대댓글내용, 대댓글작성일자
+ **자유게시판_좋아요**: 아이디, 글번호, 등급
+ **질문게시판**: 글번호, 아이디, 등급, 강의번호, 카테고리이름, 글제목, 글내용, 작성일자, 답변상태, 조회수, 좋아요, 파일, 코멘트수
+ **질문게시판_답글**: 댓글번호, 아이디, 글번호, 등급, 카테고리이름, 답변내용, 댓글작성일자, 채택여부, 파일
+ **질문게시판_대댓글**: 대댓글번호, 댓글번호, 아이디, 등급, 카테고리이름, 대댓글내용, 대댓글작성일자
+ **질문게시판_좋아요**: 아이디, 글번호
+ **공지게시판**: 글번호, 아이디, 등급, 글제목, 글내용, 작성일자
+ **문의게시판**: 글번호, 아이디, 등급, 문의제목, 문의내용, 작성일자, 답변상태, 파일
+ **문의게시판_답변**: 댓글번호, 글번호, 아이디, 등급, 댓글내용, 댓글작성일자, 파일
+ **자주묻는질문답변(FAQ)**: FAQ번호, FAQ질문, FAQ답변

</details>
<details>
<summary>

### 채팅

</summary>

![채팅](https://user-images.githubusercontent.com/80879666/208006964-42300a6e-4fcc-40da-9461-b181ab7e23df.PNG)
+ **채팅목록**: 채팅방번호, 보낸사람, 내용, 전송시간, 읽음여부
+ **채팅내용 목록**: 내용번호, 채팅방번호, 메시지주인, 메시지내용, 보낸시간
+ **1:1 멤버 채팅목록**: 채팅방번호, 보낸아이디, 받는아이디, 보낸이름, 받는이름, 내용, 전송시간, 마지막보낸사람
+ **1:1 멤버 채팅내용**: 채팅방번호, 메시지주인, 메시지내용, 보낸시간, 채팅상태
+ **실시간 알림테이블**: 알림번호, 아이디, 보낸아이디, 보여줄제목, 해당게시글번호, 카테고리

</details>
<details>
<summary>

### 결제

</summary>

![결제](https://user-images.githubusercontent.com/80879666/208007753-59da7686-1819-4906-88de-f7da6a9efbc5.PNG)
+ **결제한 강의**: 주문상세번호, 주문번호, 아이디, 강의번호, 시간표번호, 진도율, 결제상태
+ **장바구니**: 장바구니번호, 아이디, 강의번호, 시간표번호
+ **포인트로그**: 로그번호, 아이디, 주문번호, 적립포인트, 적립/사용일자
+ **주문**: 주문번호, 아이디, 결제가격, 결제일, 결제방법

</details>
<details>
<summary>

### 기타

</summary>

![기타](https://user-images.githubusercontent.com/80879666/208007410-e5f56100-0c10-43c1-affd-aa8cd3b81d19.PNG)
+ **로드맵**: 로드맵번호, 아이디, 카테고리이름, 로드맵제목, 상세내용, 강의목록, 강의자이름, 로드맵커버이미지, 로드맵담은수
+ **로드맵학습목록**: 로드맵번호, 아이디, 시작날짜, 진도율
+ **게시글신고**: 피신고자, 신고자, 신고사유, 신고일, 처리상태, 게시판종류, 해당게시판글번호
+ **신고처리(삭제된게시글)**: 삭제된글번호, 아이디, 내용, 삭제일자

</details>

## 맡은 기능(안지수)
기능 클릭 시 상세 페이지로 이동됩니다.
### 공통
+ [사용자조회 > 게시글조회](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Member/#사용자조회-게시글조회)
### 회원관리
+ [일반로그인](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Common/#일반로그인)
+ [소셜로그인 > 네이버](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Common/#소셜로그인-네이버)
+ [소셜로그인 > 구글](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Common/#소셜로그인-구글)
+ [작성글조회 > 자유주제글조회](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Member/#작성글조회-자유주제글조회)
+ [작성글조회 > 질문글조회](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Member/#작성글조회-질문글조회)
### 커뮤니티
+ [로드맵상세조회](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Lecture/#로드맵상세조회)
### 강의
+ [실시간질문](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Lecture/#)
### 강의자
+ [대시보드](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Teacher/#대시보드)
+ [강의관리](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Teacher/#강의관리)
  + [공통 > 강의추가](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Teacher/#공통-강의추가)
  + [공통 > 강의수정](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Teacher/#공통-강의수정)
  + [공통 > 수강자관리](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Teacher/#공통-수강자관리)
  + [온라인 > 실시간질문](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Teacher/#온라인-실시간질문)
  + [오프라인 > 시간표관리](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Teacher/#오프라인-시간표관리)
+ [매출조회](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Teacher/#매출조회)
  + [전체매출조회](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Teacher/#전체매출조회)
  + [강의별매출조회](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Teacher/#강의별매출조회)
+ [로드맵관리](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Teacher/#로드맵관리)
  + [로드맵작성](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Teacher/#로드맵작성)
  + [로드맵수정](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Teacher/#로드맵수정)
  + [로드맵삭제](https://github.com/gee1suu/outflearn/tree/main/src/main/webapp/Teacher/#로드맵삭제)
