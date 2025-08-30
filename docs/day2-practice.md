# Day2 Practice — Next.js, React Query, 인증, 파일 업로드, 팀 프로젝트

## 1. Commit: feat(nextjs): Next.js 프로젝트 초기화
- **뭘 배울까?**  Next.js 개발 환경 세팅
- **왜 배우지?**  SSR/SSG/CSR 하이브리드에 최적
- **배운 내용과 연결해보자!**  SPA → 서버/정적 렌더링 확장
#### 주요 학습 포인트
- app/pages 라우팅, 개발 서버, 환경 변수
#### 예제 코드
```bash
npx create-next-app@latest web
cd web && npm run dev
```
```jsx
// app/page.jsx
export default function Home(){ return <h1>Welcome to Next.js</h1>; }
```
#### 참고 자료
- Next.js Docs (https://nextjs.org/docs)

## 2. Commit: feat(nextjs): 기본 라우팅 및 SSG/SSR 페이지 추가
- **뭘 배울까?**  정적/서버 렌더링 구현
- **왜 배우지?**  UX/SEO 최적화
- **배운 내용과 연결해보자!**  데이터 캐싱과 결합
#### 주요 학습 포인트
- fetch 캐싱, 동적/정적 세그먼트
#### 예제 코드
```jsx
// app/products/page.jsx (서버 컴포넌트 예시)
export default async function ProductsPage(){ 
  const res = await fetch('http://localhost:3000/items', { cache:'no-store' });
  const items = await res.json();
  return <ul>{items.map(i => <li key={i.id}>{i.title}</li>)}</ul>;
}
```
#### 참고 자료
- Next.js 데이터 페칭 (https://nextjs.org/docs)

## 3. Commit: feat(react-query): React Query 도입 및 상품 목록 캐싱 구현
- **뭘 배울까?**  서버 상태 캐싱
- **왜 배우지?**  로딩/에러/리페치 등 표준화
- **배운 내용과 연결해보자!**  렌더+데이터 전략 완성
#### 주요 학습 포인트
- QueryClient/Provider, useQuery/useMutation
#### 예제 코드
```jsx
import {QueryClient,QueryClientProvider,useQuery} from '@tanstack/react-query';
const qc = new QueryClient();
function Products(){ 
  const {data=[],isLoading} = useQuery({ queryKey:['items'], queryFn: async()=> (await fetch('/api/items')).json() });
  return isLoading ? 'Loading...' : <ul>{data.map(i=><li key={i.id}>{i.title}</li>)}</ul>;
}
export default function App(){ return <QueryClientProvider client={qc}><Products/></QueryClientProvider>; }
```
#### 참고 자료
- TanStack Query (https://tanstack.com/query/latest/docs/react/overview)

## 4. Commit: feat(auth): JWT 기반 인증 및 보호 라우트 구현
- **뭘 배울까?**  로그인/토큰/보호 API
- **왜 배우지?**  사용자별 데이터 접근 제어
- **배운 내용과 연결해보자!**  RQ 헤더/리프레시 전략
#### 주요 학습 포인트
- Access/Refresh, 만료/재발급
#### 예제 코드
```js
app.post('/login',(req,res)=>{ /* verify */ res.json({ access:'jwt...', refresh:'jwtR...' }); });
function auth(req,res,next){ /* check header */ next(); }
app.get('/me', auth, (req,res)=> res.json({ id:1, email:'me@x.com' }));
```
#### 참고 자료
- MDN HTTP 개요 (https://developer.mozilla.org/ko/docs/Web/HTTP/Overview)

## 5. Commit: feat(auth): 구글 OAuth 로그인 설정 (passport.js)
- **뭘 배울까?**  외부 제공자 인증
- **왜 배우지?**  가입 장벽 완화
- **배운 내용과 연결해보자!**  JWT와 공존
#### 주요 학습 포인트
- OAuth2 흐름, 콜백, 세션/토큰 연계
#### 예제 코드
```js
/* passport-google-oauth20 전략 설정 의사코드 */
```
#### 참고 자료
- Passport.js (https://www.passportjs.org/)

## 6. Commit: feat(express): Multer 기반 파일 업로드 라우트 추가
- **뭘 배울까?**  업로드/검증/권한
- **왜 배우지?**  사용자 컨텐츠 핵심
- **배운 내용과 연결해보자!**  인증과 결합
#### 주요 학습 포인트
- Multer 미들웨어, 제한
#### 예제 코드
```js
const multer = require('multer'); const upload = multer({ dest:'uploads/' });
app.post('/upload', /* auth, */ upload.single('file'), (req,res)=> res.json({ ok:true, file:req.file.filename }));
```
#### 참고 자료
- Multer README (https://github.com/expressjs/multer#readme)

## 7. Commit: feat(project): 사진첩 서비스 프로젝트 구조 생성
- **뭘 배울까?**  폴더링/환경 분리
- **왜 배우지?**  기능을 제품 흐름으로 통합
- **배운 내용과 연결해보자!**  Day3 배포로 연동
#### 주요 학습 포인트
- 모노/멀티 패키지, env
#### 예제 코드
```bash
mkdir -p apps/web apps/api packages/ui
```
#### 참고 자료
- Next.js (https://nextjs.org/docs) / Express (https://expressjs.com/ko/)
