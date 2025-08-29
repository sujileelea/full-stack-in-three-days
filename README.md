# full-stack-in-three-days

3일 만에 풀스택 기초(웹 → React → Node.js → DB)를 학습하고 실습한 기록 레포입니다.  
보고서와 커밋 로그를 통해 학습 과정을 추적할 수 있습니다.

---

## 📌 학습 목표
- **Day1** : 웹 기초 (HTML, CSS, JS, Git) → React/Node.js 기초 → DB 연동
- **Day2** : 심화 (Next.js, React Query, 인증/보안, Express 심화)
- **Day3** : 배포 & 테스트 (TypeScript, AWS, Jest)

---

## 📂 프로젝트 구조
frontend/ # React (Vite)
backend/ # Express + DB
docs/ # 학습 문서 (Day별 summary & learning)
assets/ # 다이어그램, 이미지


## ▶ 실행 방법

### 프론트엔드 (React)
```bash
cd frontend
pnpm install
pnpm run dev
```

### 백엔드 (Express)
```bash
cd backend
npm install
npm run dev
```

## 🗂 문서
- [Day1 Summary](./docs/day1-summary.md)  
- [Day2 Summary](./docs/day2-summary.md)  
- [Day3 Summary](./docs/day3-summary.md)  

## 📖 참고 문서
- [MDN Web Docs](https://developer.mozilla.org/)  
- [React 공식 문서](https://react.dev/)  
- [Express 공식](https://expressjs.com/ko/)  
- [MongoDB Docs](https://www.mongodb.com/docs/)  
- [PostgreSQL Tutorial](https://www.postgresqltutorial.com/)  
- [Prisma Docs](https://www.prisma.io/docs)  

## 🗂 Commit 규칙
feat: 새로운 기능 추가
style: CSS/디자인 변경
docs: 문서 추가/수정
chore: 설정/환경 관련 작업
fix: 버그 수정
refactor: 코드 리팩토링
👉 커밋 로그만 읽어도 학습 경로가 보이도록 Day별/단계별 commit을 설계했습니다.
