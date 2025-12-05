# 🌱 Commit Challenge (깃허브 잔디 관리 챌린지)

> **"오늘 커밋 하셨나요?"**
> 매일의 커밋 내역을 확인하고, 그날의 학습 내용을 메모로 남기는 습관 형성 프로젝트입니다.

<br/>

## 📖 프로젝트 개요
**Commit Challenge**는 GitHub API를 활용하여 사용자의 당일 푸시(Push) 내역을 실시간으로 확인하고, 해당 커밋에 대한 상세 메모를 기록할 수 있는 웹 애플리케이션입니다.
백엔드 서버 없이 **LocalStorage**와 **Context API**를 활용하여 데이터 영속성과 전역 상태 관리를 구현한 **React + Vite** 프로젝트입니다.

* **배포 링크:** [https://coseung.github.io/CommitChallenge_React/](https://coseung.github.io/CommitChallenge_React/)
* **개발 인원:** 1인 (개인 프로젝트)

<br/>

## 🛠️ 기술 스택 (Tech Stack)

### Frontend
<img src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=React&logoColor=black"> <img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=Vite&logoColor=white"> <img src="https://img.shields.io/badge/Styled Components-DB7093?style=for-the-badge&logo=styled-components&logoColor=white"> <img src="https://img.shields.io/badge/React Router-CA4245?style=for-the-badge&logo=react-router&logoColor=white">

### Data & State Management
<img src="https://img.shields.io/badge/Context API-61DAFB?style=for-the-badge&logo=react&logoColor=black"> <img src="https://img.shields.io/badge/Local Storage-gray?style=for-the-badge&logo=browser&logoColor=white">

### API
<img src="https://img.shields.io/badge/GitHub REST API-181717?style=for-the-badge&logo=github&logoColor=white">

<br/>

## 📂 디렉토리 구조 (Directory Structure)

```bash
src
├── 📂 assets          # 이미지 및 정적 파일
├── 📂 components      # 전역 상태 관리 및 공통 로직
│   ├── 📄 GithubContext.jsx  # 깃허브 API 호출 및 데이터 가공
│   ├── 📄 MemoContext.jsx    # 메모 CRUD 및 로컬스토리지 동기화
│   ├── 📄 UserContext.jsx    # 로그인/회원가입 및 유저 세션 관리
│   └── 📄 useInput.jsx       # 입력 폼 핸들링 커스텀 훅
├── 📂 pages           # 페이지 컴포넌트 및 스타일
│   ├── 📄 LoginForm.jsx      # 로그인 페이지
│   ├── 📄 SignupForm.jsx     # 회원가입 (깃허브 닉네임 검증)
│   ├── 📄 PushResult.jsx     # 메인 (오늘의 잔디 확인)
│   ├── 📄 PushDetail.jsx     # 상세 (커밋 정보 확인 및 메모 작성)
│   └── 📄 MemoList.jsx       # 메모 목록 및 수정/삭제
├── 📂 routes          # 라우팅 설정
│   ├── 📄 routes.jsx         # Protected Route 구현
│   └── 📄 routesPath.js      # 경로 상수 관리
└── 📄 App.jsx         # Provider 설정
```
## ✨ 주요 기능 (Key Features)

### 1. 깃허브 잔디 확인 (GitHub API 연동)
* GitHub REST API를 호출하여 사용자의 이벤트 내역을 가져옵니다.
* 가져온 데이터 중 `PushEvent`와 `오늘 날짜`를 필터링하여 당일의 잔디 심기 여부를 시각적으로 보여줍니다.
* **API 최적화:** `PushResult` 페이지에서 데이터를 받아오면, 상세 페이지에서는 추가 API 호출 없이 전역 상태(`Context`)의 데이터를 재사용하여 로딩 시간을 단축했습니다.

### 2. 메모 기록 및 관리 (CRUD)
* 특정 커밋을 클릭하면 상세 페이지로 이동하며, 해당 커밋에 대한 메모를 작성할 수 있습니다.
* 작성된 메모는 **LocalStorage**에 저장되어 새로고침 후에도 유지됩니다.
* 메모 목록 페이지에서 수정 및 삭제가 가능합니다.

### 3. 회원가입 및 로그인 (Mock Auth)
* **GitHub 사용자 검증:** 회원가입 시 실제 GitHub에 존재하는 유저인지 API로 검증합니다.
* **LocalStorage 인증:** 별도의 DB 없이 브라우저 저장소를 활용하여 회원가입 및 로그인 로직을 구현했습니다.
* **Protected Route:** 로그인하지 않은 사용자는 메인 페이지나 상세 페이지에 접근할 수 없도록 라우터 단에서 차단합니다.

<br/>


<br/>

## 🚀 설치 및 실행 (Installation)

```bash
# 1. 레포지토리 클론
git clone [https://github.com/coseung/CommitChallenge_React.git](https://github.com/coseung/CommitChallenge_React.git)

# 2. 프로젝트 폴더로 이동
cd CommitChallenge_React

# 3. 의존성 설치
npm install

# 4. 개발 서버 실행
npm run dev

```
---
Developed by [Coseung](https://github.com/coseung)