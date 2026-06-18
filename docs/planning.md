# Flow

## 모든 내용은 대화를 통해 수정될 수 있음을 알립니다.

## 예상 기간
- 6월 18일 : 최종 기획서 완성
- 6월 26일 : 개발 완료
- 7월 1일 : 발표 준비 완료

## 왜 제작해야하는가
회의 이후 문서 작업과 업무 분담을 보다 간단하게 작업하기 위하여

## 타켓
5 - 20인의 스타트업 및 중소기업

## 단어 정의
- 프로젝트 : 기업의 진행하는 업무
- 회의 : 프로젝트의 의견 교환 및 의사 결정
- 업무 플랫폼 : 기업이 협업을 하기 위해 사용하는 협업 프로그램
- 컴펌 : AI의 회의 요약과 개별 업무 내용 확인 및 공유을 정하는 작업

## 주석
### 영문 주석 필수

## 📝 프로젝트 주석(Comment) 규칙 가이드

> **좋은 주석은 "코드가 무엇을 하는지"가 아니라 "왜 그렇게 했는지"를 설명한다.**
>
> 코드만으로 이해 가능한 내용은 주석으로 반복하지 않는다.

---

## 주석 작성 원칙

### 1. WHY를 설명한다.


코드만 봐도 알 수 있는 내용을 반복하고 있다.

#### 좋은 예시

```java
// 로그인 시 사용자 권한 검증을 위해 최신 정보를 조회한다.
User user = userRepository.findById(userId);
```

---

### 2. WHAT보다 WHY를 남긴다.

```python
# OpenAI 응답 속도를 개선하기 위해 대화 요약본만 전달한다.
summary = memory_service.get_summary()
```

---

### 3. 복잡한 로직에만 작성한다.

#### 단순한 코드

```js
const totalPrice = price + tax;
```

→ 주석 필요 없음

#### 복잡한 코드

```js
// 중복 클릭으로 인한 다중 결제를 방지하기 위해 버튼을 비활성화한다.
setIsSubmitting(true);
```

---

## TODO / FIXME 규칙

팀 프로젝트에서는 아래 네 가지 태그만 사용한다.

---

### TODO

> 앞으로 구현해야 할 기능

```java
// TODO: 소셜 로그인(Google) 연동 추가
```

---

### FIXME

> 현재 문제가 있으며 수정이 필요한 코드

```java
// FIXME: 대량 데이터 조회 시 성능 저하 발생
```

---

### HACK

> 임시 해결책

```python
# HACK: 외부 API 버그로 인해 1초 대기 후 재시도
time.sleep(1)
```

---

### NOTE

> 팀원들이 반드시 알아야 하는 사항

```js
// NOTE: 해당 API는 관리자 권한이 있어야 호출 가능
```

---

## 함수 주석 규칙

공개 API 또는 핵심 로직에는 함수 설명을 작성한다.

### Java (JavaDoc)

```java
/**
 * 사용자의 회의록 목록을 조회한다.
 *
 * @param userId 사용자 ID
 * @return 회의록 목록
 */
public List<Meeting> getMeetings(Long userId) {
    ...
}
```

---

### Python (Docstring)

```python
def generate_summary(text: str) -> str:
    """
    회의 내용을 요약한다.

    Args:
        text: 원본 회의 내용

    Returns:
        요약된 문자열
    """
```

---

### JavaScript / TypeScript (JSDoc)

```js
/**
 * 사용자 정보를 조회한다.
 *
 * @param {string} userId 사용자 ID
 * @returns {Promise<User>}
 */
async function fetchUser(userId) {
    ...
}
```

---

## 클래스 주석 규칙

핵심 역할이 명확하지 않은 경우에만 작성한다.

```java
/**
 * 회의록 생성 및 업무 자동 분배를 담당하는 서비스
 */
@Service
public class MeetingService {
    ...
}
```

---

## React 주석 규칙

### 컴포넌트

```jsx
/**
 * 회의 녹음 목록을 출력하는 컴포넌트
 */
function RecordingList() {
    ...
}
```

---

### useEffect

```jsx
// 최초 진입 시 사용자 정보를 조회한다.
useEffect(() => {
    ...
}, []);
```

---

## Spring Boot 주석 규칙

### Controller

```java
// 회의록 업로드 요청 처리
@PostMapping("/meetings")
```

---

### Service

```java
// 업무 플랫폼 연동을 위한 데이터 변환
```

---

### Repository

> 일반 CRUD에는 주석 작성하지 않는다.

---

## FastAPI 주석 규칙

```python
# RAG 검색 결과를 기반으로 응답을 생성한다.
response = rag_service.generate(...)
```

---

## 주석 작성 금지 규칙

### 코드와 동일한 설명 금지

```js
// count를 증가시킨다.
count++;
```

---

### 죽은 코드 보관 금지

```js
// old code
// doSomething();
```

> Git이 이력을 관리하므로 삭제한다.

---

### 과도한 주석 금지

```js
// if문 시작
if (...) {
    // 실행
}
```

## 주석 태그 요약

| 태그      | 용도           |
| ------- | ------------ |
| `TODO`  | 추후 구현 예정     |
| `FIXME` | 수정 필요        |
| `HACK`  | 임시 해결책       |
| `NOTE`  | 반드시 알아야 할 사항 |

## 프로젝트 네이밍 규칙 가이드

## 기본 원칙

### 1. 프로젝트마다 스타일 통일

| 언어        | 규칙                   |
| ---------- | ---------------------- |
| JavaScript | camelCase              |
| Java       | camelCase + PascalCase |
| Python     | camelCase              |
| 폴더        | kebab-case            |
| 외 파일     | camelCase              |

#### React 규칙

* React 컴포넌트 → PascalCase
* 일반 파일 / Hook → camelCase

#### JavaScript 규칙

* 모두 → camelCase

#### Spring Boot (Java) 규칙

* Class, DTO → PascalCase
* 메서드 → camelCase

#### Python 규칙

* 모두 → camelCase

### 2. 의미가 명확해야 한다

```js
getData() ❌
getUserProfile() ✅
```

### 3. 축약 금지

```js
usrInfo ❌
userInfo ✅
```

### 4. 동사 + 명사 구조 (함수)

```js
getUser()
createUser()
updateProfile()
deleteMessage()
```

### 5. 일관성 유지

* camelCase / snake_case 혼용 금지
* 프로젝트 전체에서 하나의 규칙만 사용

## 📁 폴더 & 파일 네이밍

### Frontend (React)

#### 폴더

```text
user-profile/
chat-window/
components/
```

#### 파일

```text
UserProfile.jsx
ChatWindow.jsx
apiClient.js
useAuth.js
```

## 변수 네이밍 (JavaScript)

### 변수 (camelCase)

```js
const userName = "kim";
const isLoggedIn = true;
const chatMessageList = [];
```

## 함수 네이밍

### 기본 구조: 동사 + 명사 (camelCase)

```js
getUser()
createUser()
updateProfile()
deleteMessage()
```

### 이벤트 함수 (camelCase)

```js
handleClick()
handleSubmit()
handleChange()
```

### API 함수 (camelCase)

```js
fetchUser()
fetchChatMessages()
postMessage()
```

## Spring Boot (Java)

### 클래스 (PascalCase)

```java
UserController
UserService
UserRepository
ChatService
```

### 메서드 (camelCase)

```java
getUser()
createUser()
updateUser()
deleteUser()
```

### DTO (PascalCase)

```java
UserRequestDto
UserResponseDto
ChatMessageDto
```

## Python (FastAPI)

### 파일 / 함수 (camelCase)

```python
chatService.py
vectorStore.py
```

```python
def getUserProfile():
def createMessage():
def fetchChatHistory():
```

### 클래스 (camelCase)

```python
class ChatService:
class UserRepository:
```

## 구조
![alt text](image.png)

### 구현 순서
**회의요약까지** : open source  
**액션추출 및 업무 연계** :   
1. 프로젝트에 참여한 모든 인원에게 업무 플랫폼으로 **전체 회의 내용 공지**
2. 프로젝트에 참여한 모든 인원의 업무 플랫폼으로 **개별 엄무 내용 공지**
3. 전체 회의 내용 공지 전 내용을 **총괄 1명이 컴펌**
4. 개별 업무를 업무 플랫폼의 **체크리스트로 업로드**
5. 체크리스트의 **우선 순위**
6. ~~업무 자동화 및 전체 컴펌~~

- open source는 아직 찾지 못함
- 컴퓨터가 접근이 쉬운 업무 플랫폼을 찾지 못함

### 배포 방식
기본 **웹 사이트** 배포  
시간이 남을 시 **앱** 출시

---

# Client (frontend)

### 기술 스택
- React
- vite
- Tailwindcss
- Docker
- Oauth
- Flutter (가능할 시)

### 📁 구조
__*도커로 기본 세팅 필요*__

```text
client/
├─ public/                 # 정적 파일 저장소
│
├─ src/                    # 애플리케이션 소스 코드
│  ├─ assets/              # 이미지, 아이콘 등 정적 리소스
│  │
│  ├─ App.jsx              # 최상위 애플리케이션 컴포넌트
│  ├─ App.css              # App 컴포넌트 스타일
│  ├─ main.jsx             # 애플리케이션 진입점
│  └─ index.css            # 전역 스타일 정의
│
├─ eslint.config.js        # ESLint 설정 파일
├─ tsconfig.json           # TypeScript 설정 파일
└─ .env
```

# server (backend)

### 기술 스택
- Java Spring Boot
- Docker
- Fast Api
- PostgreSQL
- Graph DB
- Vector DB

### 📁 구조
__*도커로 기본 세팅 필요*__

```text
backend/
├─ src/
│  ├─ main/
│  │  ├─ java/
│  │  │  └─ com/example/project/
│  │  │     ├─ config/              # 설정 관련 클래스
│  │  │     │
│  │  │     ├─ controller/          # API 요청 처리
│  │  │     │
│  │  │     ├─ service/             # 비즈니스 로직
│  │  │     │
│  │  │     ├─ repository/          # 데이터 접근 계층
│  │  │     │
│  │  │     ├─ entity/              # JPA 엔티티
│  │  │     │
│  │  │     ├─ dto/                 # 요청/응답 DTO
│  │  │     │
│  │  │     ├─ exception/           # 예외 처리
│  │  │     │
│  │  │     ├─ security/            # 인증/인가 관련
│  │  │     │
│  │  │     ├─ util/                # 공통 유틸리티
│  │  │     │
│  │  │     └─ ProjectApplication.java
│  │  │
│  │  └─ resources/
│  │     ├─ application.yml
│  │     ├─ static/
│  │     └─ templates/
│  │
│  └─ test/
│     └─ java/
│        └─ com/example/project/
│
├─ build.gradle
├─ settings.gradle
├─ gradlew
└─ .env
```

# AI

### 기술 스택
- Python
- LangChain

### 📁 구조
__*도커로 기본 세팅 필요*__
```text
AI/
├─ app/
│  └─ main.py
│
├─ settings.gradle
├─ gradlew
└─ .env

```