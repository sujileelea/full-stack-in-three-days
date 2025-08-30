# Day1 Overview — HTML, CSS, JS, Git, React, Express, DB 기초

<<<<<<< HEAD:docs/day1-learning.md
## 📝 학습 개요
- 학습 날짜: YYYY-MM-DD
- 학습 목표: 웹 기초부터 React/Node.js까지 풀스택의 기본 흐름 이해
- 학습 분량: 커리큘럼 1–9주차

---

## Part A — 1–4주차: 웹 기초
### 📖 이론 학습
- 웹 브라우저와 웹 표준: 
- 정적/동적 웹페이지, IP/DNS/URL: 
- HTML 문서 구조와 태그: 
- CSS 선택자, Flexbox/Grid: 
- JavaScript DOM 조작, 이벤트: 
- 비동기 처리 (fetch API): 
- Git 기본 워크플로우: 

### 💻 실습 코드 & Commit
- Commit #1 — `chore: 프로젝트 초기화`
- Commit #2 — `feat(html): 로그인 페이지 기본 마크업`
- Commit #3 — `style(css): 로그인 페이지 스타일링`
- Commit #4 — `feat(js): 로그인 이벤트 및 alert`
- Commit #5 — `feat(js): 상품 목록 API 호출 및 렌더링`
- Commit #6 — `docs(git): Git 기본 문서화`

### ✍ 느낀 점 / 어려웠던 점


---

## Part B — 5–9주차: 풀스택 기초
### 📖 이론 학습
- React (JSX, Props/State, Router): 
- Express 서버와 REST API: 
- MongoDB (문서형 DB): 
- PostgreSQL (관계형 DB): 
- Prisma ORM 기본기: 

### 💻 실습 코드 & Commit
- Commit #7 — `feat(react): Vite 기반 React 프로젝트 초기화`
- Commit #8 — `feat(react): 상품 목록 컴포넌트 구현`
- Commit #9 — `feat(react): 상품 등록 폼 추가`
- Commit #10 — `feat(router): React Router 적용`
- Commit #11 — `feat(api): Express 서버 초기 설정 및 상품 API 구현`
- Commit #12 — `feat(db): MongoDB 연결 및 상품 Schema 설계`
- Commit #13 — `feat(db): PostgreSQL + Prisma ORM 모델링`
- Commit #14 — `chore(env): 환경 변수 및 서버 설정 분리`
- Commit #15 — `docs(day1): Day1 학습 정리 문서화`

### ✍ 느낀 점 / 어려웠던 점


---

## 📌 커밋과 연결
- 커밋 메시지와 코드 스니펫을 연결해 기록

---

## 🗂 참고 자료
- [MDN Web Docs](https://developer.mozilla.org/)
- [React 공식 문서](https://react.dev/)
- [Express 공식](https://expressjs.com/ko/)
- [MongoDB Docs](https://www.mongodb.com/docs/)
- [PostgreSQL Tutorial](https://www.postgresqltutorial.com/)
- [Prisma Docs](https://www.prisma.io/docs)
=======
## 1. Commit: feat(html): 로그인/회원가입 기본 마크업 추가
- **뭘 배울까?**  
  HTML 시맨틱 태그를 이용해 로그인·회원가입 같은 기본 구조를 만든다
- **왜 배우지?**  
  모든 웹 서비스는 사용자 인증 과정을 기본 전제로 하며, 이 단계가 웹 개발의 출발점이다
- **배운 내용과 연결해보자!**  
  웹 문서 구조를 이해한 뒤 → CSS로 시각적 UI를 입히고 → JavaScript로 동적인 동작을 추가한다

## 2. Commit: style(css): 기본 레이아웃 및 폼 스타일 적용
- **뭘 배울까?**  
  CSS 선택자와 Flex/Grid를 이용해 UI를 꾸민다
- **왜 배우지?**  
  HTML만으로는 단순 텍스트일 뿐이다. CSS는 웹을 **사람이 쓰기 좋은 화면**으로 만든다
- **배운 내용과 연결해보자!**  
  HTML 구조에 스타일을 입히고 → 이후 JavaScript로 동적인 상호작용을 붙인다

## 3. Commit: feat(js): 로그인 이벤트 및 외부 상품 API 호출 로깅
- **뭘 배울까?**  
  JavaScript로 DOM 조작, 이벤트 핸들링, 비동기 처리(Fetch API)를 배운다
- **왜 배우지?**  
  정적인 HTML/CSS만으로는 한계가 있다. JS는 **웹을 동적 애플리케이션**으로 바꿔준다
- **배운 내용과 연결해보자!**  
  CSS까지는 UI → JS로 데이터 상호작용 → 뒤이어 React에서 구조적으로 관리

## 4. Commit: docs(git): Git 기본 워크플로/메시지 규칙 문서화
- **뭘 배울까?**  
  Git과 Unix 명령어를 통해 버전 관리와 협업을 배운다
- **왜 배우지?**  
  코드가 길어지고 협업자가 늘어나면 반드시 **이력 관리 체계**가 필요하다
- **배운 내용과 연결해보자!**  
  JS로 동작을 만들며 복잡성 증가 → Git으로 관리 → React/Node 단계에서 협업 필수 기반

## 5. Commit: feat(react): Vite 기반 React 프로젝트 초기화
- **뭘 배울까?**  
  React 개발 환경을 Vite로 세팅한다
- **왜 배우지?**  
  React는 상태와 UI를 체계적으로 관리하는 대표적인 프레임워크다
- **배운 내용과 연결해보자!**  
  DOM 직접 제어(JS)의 한계를 체감한 후 → React로 컴포넌트/상태 기반 사고를 배운다

## 6. Commit: feat(react): 상품 목록 컴포넌트와 상태/검색 구현
- **뭘 배울까?**  
  React 상태 관리와 UI 렌더링 흐름
- **왜 배우지?**  
  서비스는 항상 데이터와 연결되며, 상태 변화가 즉시 UI에 반영되어야 한다
- **배운 내용과 연결해보자!**  
  React 프로젝트 구조를 익힌 뒤 → 상태 기반으로 데이터 표시 → 폼 입력과 등록 기능으로 확장한다

## 7. Commit: feat(react): 상품 등록 폼 및 간단 화면 전환(토글) 구현
- **뭘 배울까?**  
  Controlled Components로 입력값을 상태로 관리하고, 화면 전환 로직을 구현한다
- **왜 배우지?**  
  데이터 입력/수정은 실제 서비스다운 동작의 핵심이다
- **배운 내용과 연결해보자!**  
  데이터 읽기(목록) → 데이터 생성(폼) → 서버 API와 연동하는 단계로 확장한다

## 8. Commit: feat(api): Express 서버 초기 설정 및 상품 API(GET/POST) 구현
- **뭘 배울까?**  
  Node.js/Express로 API 서버를 만들고, 데이터를 주고받는다
- **왜 배우지?**  
  프론트엔드만으로는 공유나 저장이 불가능하다. 백엔드가 있어야 실제 서비스가 된다
- **배운 내용과 연결해보자!**  
  프론트 입력값을 서버로 전송 → DB를 붙여 데이터를 영구 저장하는 단계로 나아간다

## 9. Commit: feat(router): React Router 적용 및 페이지 분리 (선택)
- **뭘 배울까?**  
  React Router로 페이지 기반 화면 전환을 구현한다
- **왜 배우지?**  
  규모가 커지면 단순 토글은 한계. URL 기반 라우팅은 확장성과 사용자 경험을 보장한다
- **배운 내용과 연결해보자!**  
  간단한 전환 → 라우터 → Next.js 라우팅 학습으로 이어진다

## 10. Commit: feat(db): MongoDB Atlas 연동 및 상품 CRUD 기본 골격 (선택)
- **뭘 배울까?**  
  NoSQL DB와 연결해 데이터를 영구 저장한다
- **왜 배우지?**  
  서버 메모리 저장은 휘발성이다. DB는 지속성과 확장성을 보장한다
- **배운 내용과 연결해보자!**  
  API로 주고받던 데이터를 DB에 저장 → 뒤에 Prisma/Postgres로 구조화된 모델을 배운다

## 11. Commit: feat(db): PostgreSQL + Prisma ORM 모델링 및 /posts 조회 예시 (선택)
- **뭘 배울까?**  
  Prisma ORM으로 관계형 DB(PostgreSQL)를 모델링하고 타입 안전 쿼리를 사용한다
- **왜 배우지?**  
  구조가 명확한 DB는 데이터 무결성과 관계 표현에 강하다
- **배운 내용과 연결해보자!**  
  MongoDB의 유연성 → Postgres의 안정성 → 뒤이어 TypeScript와 결합해 안전성이 강화된다
>>>>>>> 87bf17d (docs: Day1, Day2, Day3에 해당하는 overview.md, practice.md 파일 생성 및 업데이트):docs/day1-overview.md
