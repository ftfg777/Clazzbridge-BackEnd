# 🎓 ClazzBridge

## 클라우드 플랫폼(K-PaaS) 기반 서비스 개발 아이디어 공모전 출품작

---

<br>

## 🌟 Description
![6](https://github.com/user-attachments/assets/99b99976-dde7-4087-bd99-9a2862d5c37f)


### 🏆 목적/동기
네이버클라우드캠프 수강 중 강사와 수강생의 소통 문제, 학원의 수업 관리 문제를 직접 느끼고 개선된 학습 환경을 제공하고자 서비스를 개발하게 되었습니다.

<br>

### 🚀 기대 효과
학습 성과 향상, 강사-학생 간 신뢰 강화, 수업 운영 효율성 증대, 학습 공동체 활성화와 같은 긍정적인 변화를 기대할 수 있습니다.

<br>

### 📅 프로젝트 기간 / 인원
- **프로젝트명** : ClazzBridge
- **진행 기간** : 2024.08 ~ 2024.11 (3개월)
- **인원**: 5명
- **팀원**:
- Common Role : FullStack & DevOps
  - **강슬기** [![GitHub](https://img.shields.io/badge/GitHub-@github-181717?style=flat&logo=github)](https://github.com/seulki-k)
  - **권준성** [![GitHub](https://img.shields.io/badge/GitHub-@github-181717?style=flat&logo=github)](https://github.com/infra-kwon)
  - **임상우** [![GitHub](https://img.shields.io/badge/GitHub-@github-181717?style=flat&logo=github)](https://github.com/tkddn0321)
  - **정찬우** [![GitHub](https://img.shields.io/badge/GitHub-@github-181717?style=flat&logo=github)](https://github.com/ftfg777)
  - **최동인** [![GitHub](https://img.shields.io/badge/GitHub-@github-181717?style=flat&logo=github)](https://github.com/Bulgogi-Pizza)

- **활용 기술**
    - 메인 백엔드 - Java, Spring [Boot, Security, Data JPA], REST API, MySQL, Mapstruct
    - 웹소켓 백엔드 - Node.js, express, Socket.IO, redis, Axios
    - 프론트엔드 - React, Redux, Material UI, Axios, Socket.IO
    - 공통 - Role-based Access Control, JWT
---

<br>

## 🛠️ Techs Used

### Back-end
- **Java 11**
- **Spring Boot 2.7.3**
- **Gradle**
- **Spring Data JPA**
- **MySQL 8.0**
- **Lombok**
- **RESTful API**
- **Mapstruct**

### Back-end WebSocket
- **Node.js**
- **express**
- **Socket.Io**
- **redis**

### Front-end
- **React**
- **JavaScript**
- **jQuery**
- **HTML 5**
- **MUI**
- **Axios**
- **Socket.Io**

### Database
- **MySQL 8.0**
- **Redis**

### Server & Deployment
- **Apache Tomcat v9.0**
- **Naver Cloud Platform**

### CI/CD
- **GitHub Actions**
- **Docker**
- **Jenkins**

### Security
- **Spring Security**
- **JWT**

### API
- **RESTful API**

### Collaboration
- **Github**
- **Notion**
- **Slack**

---

<br>

## 📐 Project Design

![43](https://github.com/user-attachments/assets/5672c8ef-2404-4137-a8d1-186c725eeac9)


![14](https://github.com/user-attachments/assets/e292a837-ad97-491e-91f6-3f4b46e789c3)


### ERD
<img width="952" alt="image" src="https://github.com/user-attachments/assets/5f53bd49-665e-40c5-855c-d21cc8a98ecc" />


![47](https://github.com/user-attachments/assets/d9cd5fa0-f0b3-48c5-9cc7-5cc5ad3c8e44)

---

<br>

## 🔍 Specific Description

### 로그인

![16](https://github.com/user-attachments/assets/40147de5-a1a7-486b-a8b1-b2675926567d)


- JWT 인증 확인 메서드 제작 (풀스택)
    - 액세스 토큰 유효 시
        1. 클라이언트의 API 요청 헤더에 실린 액세스 토큰이 유효한지 검사 (백엔드)
        2. 유효할 경우 True 반환 및 API 실행 (백엔드)
    - 액세스 토큰 무효, 리프레쉬 토큰 유효 시
        1. 클라이언트의 API 요청 헤더에 실린 액세스 토큰이 유효한지 검사 (백엔드)
        2. 유효하지 않을 경우 False 반환 (백엔드)
        3. False 반환 시 쿠키에 실린 리프레쉬 토큰을 백엔드에 검사 및 액세스 토큰 발급 요청 (프론트엔드)
        4. 리프레쉬 토큰 유효 시 True 반환 및 액세스 토큰 재발급 (백엔드)
        5. True 반환 시 발급된 액세스 토큰과 함께 API 재요청 (프론트엔드)
        6. 액세스 토큰 검사 후 요청 API 실행 (백엔드)
    - 액세스 토큰 무효, 리프레쉬 토큰 무효 시
        1. 클라이언트의 API 요청 시 헤더에 실린 액세스 토큰이 유효한지 검사 (백엔드)
        2. 유효하지 않을 경우 False 반환 (백엔드)
        3. False 반환 시 쿠키에 실린 리프레쉬 토큰을 백엔드에 검사 및 액세스 토큰 발급 요청 (프론트엔드)
        4. 리프레쉬 토큰 무효 시 False 반환 (백엔드)
        5. False 반환 시 로그아웃 후 로그인 페이지로 이동 (프론트엔드)
- Spring Security와 JWT를 사용한 사용자 인증 방식 구현
- DB 데이터와 비교 후 인증 실패 시 오류 메시지 출력

### 대시보드

![18](https://github.com/user-attachments/assets/d77545bc-0ba1-46b5-80ac-3a6ac4f0fa85)


- 로그인 시 마주하게 되는 페이지
- Role-based Access Control 예외처리 (백엔드)
    - 매니저는 강의 진행 상황이 보이지 않고, 캘린더의 모든 데이터 접근 가능
    - 강사와 수강생은 강의 진행 상황이 보이고, 소속 강의와 학원 전체 일정 데이터만 접근 가능
- 외부 API 연결, 위치 기반 서비스
    - OpenWeather API로 현재 접속 지역의 날씨 정보 제공

### 강의실

![35](https://github.com/user-attachments/assets/73a27dd7-ea09-4ecf-ac3d-65db5a95804b)


- 이해 완료, 손 들기, 온라인의 상태 관리 기능 (풀스택)
    - 본인의 이해도 및 손 들기 상태를 Floating Action Button을 눌러 표현 (수강생)
    - 수강생들의 이해도와 손 들기, 온라인의 상태를 실시간으로 확인 (강사)
    - WebSocket으로 통신하여 실시간으로 조회 가능
    - redis-client를 통한 redis 데이터 접근
- 학생의 현재 상태 및 좌석 배치 조회
    - 학생 이해도, 손 들기 확인 (강사)
    - 본인의 상태 확인, 타 학생 프로필 조회 (수강생)

### 질의응답 게시판

![33](https://github.com/user-attachments/assets/d311a722-237a-4f6b-b649-4e45a24bc611)


- 질의응답 CRUD 기능 구현 (백엔드)
    - RESTful API 구조 준수
    - 답변 CRUD 기능 구현 (강사)
    - 질문 CRUD 기능 구현 및 본인 질문에 대해서만 UD 가능 (수강생)
- Role-based Access Control 예외처리 (풀스택)
    - 프론트엔드에서 권한별 UI 차이 구현
    - 백엔드에서 권한에 맞지 않는 API 요청 시 에러 반환
    - 타인의 질문에 API 요청 시, 액세스 토큰과 비교하여 인증 실패 오류 반환

### 투표

![21](https://github.com/user-attachments/assets/d9b7a512-a5fb-49d2-aea8-ccf5b1702548)


- 투표 날짜와 제목, 내용 데이터를 받아 투표 생성 (강사)
- 투표 리스트 중 투표를 선택하여 투표 가능 (수강생)
- Role-based Access Control - 권한에 맞지 않는 액션 수행 시 오류 발생

### 커뮤니티

![커뮤니티](https://github.com/user-attachments/assets/b706e081-dc5e-45ce-8c32-f686799030ce)


- 질문, 공지사항, 피드백 등의 카테고리 구성
- 공지사항은 최상단에 고정
- 사용자 입력이 0.5s 멈췄을 때 검색 기능 구현 (디바운싱)
- 카테고리별 필터링 가능

### 과제

![과제](https://github.com/user-attachments/assets/1394db5c-a6c2-47c8-a393-d1a0637ab71d)


- 진행 중, 마감 당일, 마감된 과제 확인 가능
- 리액트 퀼 에디터로 과제 제출 가능 (수강생)
- 학생별 제출 상태를 확인 가능 (강사)
- 과제 생성 가능 (강사)

### 캘린더

![23](https://github.com/user-attachments/assets/ebff2a7a-f078-4a53-a75f-e82fbf261202)


- 일정 날짜와 제목, 내용 데이터를 받아 일정 생성 (강사, 매니저)
- 수강생은 일정 조회만 가능 (수강생)
- 일정 시작 날짜와 끝 날짜가 맞지 않는 경우 오류 발생
- Role-based Access Control - 권한에 맞지 않는 액션 수행 시 오류 발생

### 회원 관리

![26](https://github.com/user-attachments/assets/c3502c33-ddbb-4c8f-b0c9-800a30dc4046)


- 관리자 계정만 접근 및 관리 가능
- 아이디, 이메일 등 Key에 대한 중복 예외처리 (프론트엔드)
- API직접 요청으로 등록 요청 시에도 JWT 기반 예외처리 (백엔드)

### 강의 및 강의실 관리

![28](https://github.com/user-attachments/assets/52ccf367-68d6-4c95-98b5-f88e53fd3be6)


- 관리자 계정만 접근 및 관리 가능
- 강의실 이름, 사용중인 강의실 등에 대한 중복 예외처리 (프론트엔드)
- API직접 요청으로 등록 요청 시에도 JWT와 DB 기반 예외처리 (백엔드)

### 채팅 기능

![41](https://github.com/user-attachments/assets/be8af7f1-d885-4cc2-8866-df771c65e9e3)


- WebSocket으로 통신하여 실시간 채팅 구현 (풀스택)
- Role-based Access Control 예외처리
    - 채팅은 수강생과 강사가 속한 강의 멤버 혹은 매니저만 채팅 가능하도록 예외처리
- redis DB 설계
    - redis-client를 통한 redis 데이터 접근
    - ChatRoom:Id, ChatRoom:Id:Messages, User:Id로 redis 데이터 Key 구성

<br>

# CI/CD 파이프라인 구성

![47](https://github.com/user-attachments/assets/78d493d9-7c3a-4fa8-9053-dde5f05ab474)


1. Git 코드 변경 (Git push)
2. 젠킨스에서 Github WebHook으로 코드 변경 인식
3. 새로운 코드로 jar 빌드 및 docker 이미지 생성
4. 생성된 이미지 Docker Hub에 푸시
5. SSH 키 인증과 함께 Docker Hub에 푸시된 이미지로 새 프론트엔드 컨테이너 빌드
6. 업데이트 및 배포 완료

<br>

# 리팩토링 및 디버깅

1. **채팅방 생성을 위한 같은 강의실 소속의 멤버와 강사, 매니저 데이터 요청 시 시간이 오래걸리는 문제 식별 (백엔드)**
    - Spring Data JPA로 MySQL에 복잡한 로직의 데이터 요청 시 Query문이 길게 작성되는 문제 식별
    
    → LeftJoin, Where, Select를 직접 사용해 Query문 작성 및 최적화
   
    → Query문 길이 축소 (100줄 → 6줄)
   
    → 실행 시간 단축 (약 40%)
    
3. **React 컴포넌트 진입 구조가 의도와 다르게 설계되고, 전역 상태 관리가 존재하지 않아 상태 관리가 어려운 문제 식별 (프론트엔드)**

    → FrontEnd의 전체 컴포넌트 구조를 실행 순서에 따라 리팩토링
   
    → 전역 상태 관리를 위한 Redux 사용
   
    → App 컴포넌트를 [Socket, Login, User] Provider로 감싸 전역으로 관리
    
4. **새로고침 시 UserData 소실 문제 (프론트엔드)**
    - 새로고침 시 React 컴포넌트가 모두 언마운트된 후 재마운트
    - 재마운트 과정에서 UserData UseState 초기값인 null로 값 초기화
    
    → UserData UseState 초기값을 LocalStorage에서 가져오도록 설정
    
5. **LocalStorage 값을 임의로 수정 시 서비스에 영향을 미침 (프론트엔드)**
    - LocalStorage에서 데이터를 재가공하는 로직 발견
    
    → LocalStorage 데이터는 단순 참조용으로 사용.
    
    → 재가공할 데이터는 Redux를 도입하여 새로고침 시 데이터를 백엔드로부터 Fetching하도록 로직 변경
    
6. **채팅방에서 새로고침 시 소켓 연결이 끊긴 상태에서 데이터 요청 시도 (프론트엔드)**
    - 새로고침 후 소켓 재연결을 시도하나, 데이터 요청보다 재연결이 느린 동기처리 오류 발견
    - 소켓 재연결 조건이 SocketProvider 컴포넌트 마운트 시로 되어있음을 발견
    
    → 소켓을 사용한 데이터 요청(socket.emit())시 
    
    → socket.connected() 메서드 확인
    
    → False 시 재연결 timeout 5초 내에 재연결 요청
    
    → 데이터 요청 재시도
    
    → False 시 에러 반환

# ☑️ 프로젝트 성과 및 배운점

- **프로젝트 개발 파이프라인의 중요성 경험**
    - 초반엔 떠오르는 대로, 요구사항을 설계하고 UseCase 설계 후 프로토타입을 제작한 뒤 개발을 진행하였습니다. 하지만 개발에 필요한 구조가 제대로 확립되지 않아 여러 번 구조를 변경하며 프로젝트 진행에 큰 차질을 빚었습니다.
    - 결국 부트캠프를 진행하며 배운 개발 구조를 채택해 간단한 프로토타입 제작 후 UseCase를 액터별로 식별하였습니다. 그 후 와이어 프레임을 실서비스에 가깝게 설계한 뒤 DB 모델링을 진행하고 개발을 시작하였습니다.
    - 그 결과 DB모델링에 따라 DDL과 Domain을 먼저 구현한 뒤, UseCase에 따라 Controller와 Service를 구현하니 프로젝트의 진행이 훨씬 매끄럽고 변경 사항이 적어 빠른 개발이 가능했습니다. 이를 통해 개발의 순서가 얼마나 중요한 지 몸소 느낄 수 있었습니다.
- **프로젝트 구현 시 프로젝트 구조 확립의 중요성**
    - 첫 프로젝트 개발이기에 프로젝트 구조 개념이 확립되지 않은 상태에서 프로젝트를 시작했습니다.
    - 그렇게 프로젝트 내에서 Domain, Controller, Service의 분리 없이 통째로 진행하던 중 코드 변경 시 복잡성 증가로 오류 발생이 쉽고 디버깅이 어려운 문제가 발생했습니다.
    - 이를 해결하기 위해 프로젝트 회의를 진행하여 Domain, Controller, Service, Util Method, RESTful API의 구조를 따르기로 결정하였습니다. 그 후 유지보수가 훨씬 용이해짐을 발견했고, 객체지향의 기본 원칙인 SOLID 원칙을 준수할 수 있었습니다.
- **소통의 중요성 경험**
    - 같은 회의를 해도 각자 생각한 기준과 주관이 달라 소통의 간격이 넓을수록 문제가 발생한다는 것을 발견하였습니다.
    - 이를 해결하기 위해 팀원 간의 소통 주기를 줄여 더 잦은 대화를 이끌어 주관 차이를 줄였습니다. 또한 말하지 않아도 괜찮겠지, 하는 사소한 부분까지 모두 소통해야 함을 깨닫고 프로젝트와 관련된 사소한 변경 사항을 모두 소통하였습니다.
    - 그 결과 소통의 차이를 줄일 수 있었고, 팀내 소통의 오류를 줄여 불화의 위기도 줄일 수 있었습니다. 이를 통해 소통의 빈도를 줄이는 것의 중요성, 주관 차이에 대한 이해도를 높일 수 있었습니다.

---
