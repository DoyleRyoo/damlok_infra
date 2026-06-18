# damlok_frontend

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
frontend/
├─ public/                 # 정적 파일 저장소
│
├─ src/                    # 애플리케이션 소스 코드
│  ├─ assets/              # 이미지, 아이콘 등 정적 리소스
│  │
│  ├─ App.tsx              # 최상위 애플리케이션 컴포넌트
│  ├─ App.css              # App 컴포넌트 스타일
│  ├─ main.tsx             # 애플리케이션 진입점
│  └─ index.css            # 전역 스타일 정의
│
├─ eslint.config.js        # ESLint 설정 파일
├─ tsconfig.json           # TypeScript 설정 파일
└─ .env
```
