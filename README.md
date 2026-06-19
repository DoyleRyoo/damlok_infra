# damlok_infra

## frontend

1. 프로젝트 생성

```bash
npm create vite@latest frontend -- --template react-ts
cd frontend
npm init -y
```

2. 기본 의존성 설치

```bash
npm install axios react-router-dom zustand react-media-recorder react-hot-toast lucide-react dayjs @supabase/supabase-js
```

3. TailwindCSS v3 설치

```bash
npm install -D tailwindcss@3 postcss autoprefixer
npx tailwindcss init -p
```

4. 개발 의존성 설치

```bash
npm install -D prettier prettier-plugin-tailwindcss eslint eslint-config-prettier
```

---

## backend

1. 프로젝트 생성
   Spring Initializr 설정

```bash
Project      : Maven
Language     : Java
Spring Boot  : 3.5.x
Java         : 17
Packaging    : Jar

Group        : com.example
Artifact     : backend
Name         : backend
Package Name : com.example.backend
```

2. Spring Initializr에서 선택할 의존성

```bash
Spring Web
Spring Data JPA
Validation
OAuth2 Client
PostgreSQL Driver
Lombok
Spring Boot Actuator
```

3. pom.xml 추가 의존성
   Spring Initializr에서 생성된 pom.xml에 아래 의존성을 추가한다.

```html
<!-- Swagger/OpenAPI -->
<dependency>
  <groupId>org.springdoc</groupId>
  <artifactId>springdoc-openapi-starter-webmvc-ui</artifactId>
  <version>2.8.9</version>
</dependency>

<!-- Supabase JWT 검증 -->
<dependency>
  <groupId>com.auth0</groupId>
  <artifactId>java-jwt</artifactId>
  <version>4.5.0</version>
</dependency>
```

4. 최종 pom.xml 의존성 목록

```bash
spring-boot-starter-web
spring-boot-starter-data-jpa
spring-boot-starter-validation
spring-boot-starter-security
spring-boot-starter-oauth2-client
spring-boot-starter-actuator
postgresql
lombok
springdoc-openapi-starter-webmvc-ui
java-jwt
```

---

## AI

1. Python 설치

Python 3.12 다운로드 및 설치

https://www.python.org/downloads/

설치 시 반드시 체크

```
☑ Add Python to PATH
```

설치 확인

```bash
python --version
pip --version
```

2. 프로젝트 생성

```bash
mkdir ai
cd ai

python -m venv venv
```

가상환경 활성화

Windows

```bash
venv\Scripts\activate
```

Mac/Linux

```bash
source venv/bin/activate
```

3. 모든 의존성 설치

```bash
pip install fastapi uvicorn
pip install langchain langchain-community langchain-anthropic langchain-postgres
pip install anthropic
pip install openai-whisper ffmpeg-python
pip install sentence-transformers
pip install psycopg2-binary pgvector
pip install notion-client
pip install python-multipart
pip install pydantic-settings python-dotenv
pip install tiktoken httpx
```

---

## Supabase

프로젝트 생성 후 활성화

```SQL
create extension if not exists vector;
```

---

## PostgreSQL 벡터 컬럼 예시

```SQL
embedding vector(1024)
```
