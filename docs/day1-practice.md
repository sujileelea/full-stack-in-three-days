# Day1 Practice — HTML, CSS, JS, Git, React, Express, DB 기초

## 1. Commit: feat(html): 로그인/회원가입 기본 마크업 추가
- **뭘 배울까?**  HTML 시맨틱 태그로 로그인·회원가입 기본 구조 만들기
- **왜 배우지?**  인증 흐름은 모든 서비스의 출발점
- **배운 내용과 연결해보자!**  HTML 구조 → CSS 시각화 → JS 동작

#### 주요 학습 포인트
- HTML 문서 구조, 시맨틱 태그, 정적 vs 동적, URL/IP/DNS 개념
#### 예제 코드
```html
<!DOCTYPE html>
<html lang="ko"><head><meta charset="UTF-8"><title>중고마켓 - 로그인</title></head>
<body>
  <main>
    <h1>로그인</h1>
    <form id="login" novalidate>
      <label>아이디 <input name="id" placeholder="이메일 혹은 사용자명" required /></label>
      <label>비밀번호 <input name="pw" type="password" placeholder="비밀번호" required /></label>
      <button type="submit">로그인</button>
    </form>
    <p><a href="./signup.html">회원가입</a></p>
  </main>
</body></html>
```
#### 참고 자료
- MDN: HTML 소개 (https://developer.mozilla.org/ko/docs/Learn/HTML/Introduction_to_HTML)  
- MDN: 시맨틱 HTML (https://developer.mozilla.org/ko/docs/Glossary/Semantics#semantics_in_html)  
- MDN: URL이란 (https://developer.mozilla.org/ko/docs/Learn/Common_questions/Web_mechanics/What_is_a_URL)

## 2. Commit: style(css): 기본 레이아웃 및 폼 스타일 적용
- **뭘 배울까?**  CSS 선택자, Flex/Grid로 UI 구성
- **왜 배우지?**  사용성 있는 화면을 만들기 위해
- **배운 내용과 연결해보자!**  구조(HTML) 위에 스타일(CSS) → 동작(JS)

#### 주요 학습 포인트
- 선택자, 상속/우선순위, Flexbox/Grid, 색/타이포/간격 토큰
#### 예제 코드
```css
:root { --gap:12px; --brand:#2563eb; --bg:#fafafa; }
body { font-family:sans-serif; background:var(--bg); margin:0; }
main { max-width:420px; margin:5vh auto; padding:24px; background:#fff; border-radius:12px; box-shadow:0 6px 18px rgba(0,0,0,.08); }
form { display:flex; flex-direction:column; gap:var(--gap); }
button { background:var(--brand); color:#fff; border:none; padding:10px; border-radius:8px; }
```
#### 참고 자료
- MDN: CSS 첫걸음 (https://developer.mozilla.org/ko/docs/Learn/CSS/First_steps)  
- MDN: Flexbox (https://developer.mozilla.org/ko/docs/Learn/CSS/CSS_layout/Flexbox) / Grid (https://developer.mozilla.org/ko/docs/Learn/CSS/CSS_layout/Grids)

## 3. Commit: feat(js): 로그인 이벤트 및 외부 상품 API 호출 로깅
- **뭘 배울까?**  DOM 조작, 이벤트, 비동기(Fetch) 처리
- **왜 배우지?**  정적 페이지를 동적 앱으로 전환
- **배운 내용과 연결해보자!**  CSS→JS→React

#### 주요 학습 포인트
- DOM API, 이벤트, 모듈, async/await, 오류처리
#### 예제 코드
```js
document.getElementById('login').addEventListener('submit', (e) => { 
  e.preventDefault();
  const fd = new FormData(e.currentTarget);
  alert(`로그인 시도: ${fd.get('id')}`);
});
async function loadProducts(){ 
  const res = await fetch('https://fakestoreapi.com/products');
  if(!res.ok) throw new Error('API 오류');
  const data = await res.json();
  console.log('[products]', data);
}
loadProducts();
```
#### 참고 자료
- MDN: DOM (https://developer.mozilla.org/ko/docs/Web/API/Document_Object_Model/Introduction) / 이벤트 (https://developer.mozilla.org/ko/docs/Learn/JavaScript/Building_blocks/Events)  
- MDN: Fetch (https://developer.mozilla.org/ko/docs/Web/API/Fetch_API/Using_Fetch) / 비동기 (https://developer.mozilla.org/ko/docs/Learn/JavaScript/Asynchronous) / 모듈 (https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Modules)

## 4. Commit: docs(git): Git 기본 워크플로/메시지 규칙 문서화
- **뭘 배울까?**  버전 관리와 협업, 메시지 규칙
- **왜 배우지?**  변경 이력을 체계적으로 기록/공유
- **배운 내용과 연결해보자!**  복잡성 ↑ → Git으로 질서

#### 주요 학습 포인트
- init/add/commit/push, 브랜치/PR, Conventional Commits
#### 예제 코드
```bash
git init && git add .
git commit -m "feat(html): 로그인/회원가입 기본 마크업 추가"
git branch -M main
git remote add origin <repo-url>
git push -u origin main
```
#### 참고 자료
- Pro Git (https://git-scm.com/book/ko/v2) / Conventional Commits (https://www.conventionalcommits.org/ko/v1.0.0/)

## 5. Commit: feat(react): Vite 기반 React 프로젝트 초기화
- **뭘 배울까?**  Vite로 React 개발 환경 구성
- **왜 배우지?**  빠른 HMR, 설정 간결, 현대적 번들
- **배운 내용과 연결해보자!**  DOM 직접 조작의 한계 → React

#### 주요 학습 포인트
- Vite 생성/스크립트, JSX, 폴더 구조
#### 예제 코드
```bash
npm create vite@latest frontend -- --template react
cd frontend && npm install && npm run dev
```
```jsx
// src/App.jsx
export default function App(){ return <h1>중고마켓</h1>; }
```
#### 참고 자료
- Vite 가이드 (https://vitejs.dev/guide/) / React 학습 (https://react.dev/learn)

## 6. Commit: feat(react): 상품 목록 컴포넌트와 상태/검색 구현
- **뭘 배울까?**  useState/useEffect, 리스트/검색 렌더
- **왜 배우지?**  상태→UI 반영의 기본
- **배운 내용과 연결해보자!**  읽기→입력/등록

#### 주요 학습 포인트
- 상태/이펙트, key, 필터, 입력 제어
#### 예제 코드
```jsx
import {useEffect,useMemo,useState} from 'react';
export default function Products(){
  const [items,setItems]=useState([]), [q,setQ]=useState('');
  useEffect(()=>{(async()=>{const r=await fetch('http://localhost:3000/items'); setItems(await r.json());})()},[]);
  const filtered=useMemo(()=>items.filter(i=>i.title?.toLowerCase().includes(q.toLowerCase())),[items,q]);
  return (<main><h2>상품 목록</h2><input value={q} onChange={e=>setQ(e.target.value)} placeholder="검색"/><ul>{filtered.map(i=><li key={i.id}>{i.title}</li>)}</ul></main>);
}
```
#### 참고 자료
- React Docs (https://react.dev/learn)

## 7. Commit: feat(react): 상품 등록 폼 및 간단 화면 전환(토글) 구현
- **뭘 배울까?**  Controlled input, 폼 검증/제출
- **왜 배우지?**  생성/수정 플로의 핵심
- **배운 내용과 연결해보자!**  읽기→생성→서버 저장

#### 주요 학습 포인트
- 입력 상태, 숫자 변환, 성공 후 리셋
#### 예제 코드
```jsx
import {useState} from 'react';
export default function NewItem(){
  const [title,setTitle]=useState(''), [price,setPrice]=useState('');
  async function submit(e){ e.preventDefault();
    const payload={ title:title.trim(), price:Number(price) };
    if(!payload.title||Number.isNaN(payload.price)) return alert('입력 확인');
    await fetch('http://localhost:3000/items',{ method:'POST', headers:{'Content-Type':'application/json'}, body:JSON.stringify(payload)});
    setTitle(''); setPrice(''); alert('저장');
  }
  return (<form onSubmit={submit}><input value={title} onChange={e=>setTitle(e.target.value)} placeholder="상품명"/><input value={price} onChange={e=>setPrice(e.target.value)} type="number" placeholder="가격"/><button>등록</button></form>);
}
```
#### 참고 자료
- React Docs (https://react.dev/learn)

## 8. Commit: feat(api): Express 서버 초기 설정 및 상품 API(GET/POST) 구현
- **뭘 배울까?**  Express, JSON 파서, CORS, 라우팅
- **왜 배우지?**  프론트-백 데이터 교환 기반
- **배운 내용과 연결해보자!**  상태를 서버에 저장/공유

#### 주요 학습 포인트
- express.json(), GET/POST, 에러 응답
#### 예제 코드
```js
const express=require('express'); const cors=require('cors'); const app=express();
app.use(cors()); app.use(express.json());
let items=[{ id:1, title:'예시', price:10000 }];
app.get('/items',(req,res)=>res.json(items));
app.post('/items',(req,res)=>{ const {title,price}=req.body||{}; if(!title||Number.isNaN(Number(price))) return res.status(400).json({error:'bad'});
  const it={ id:Date.now(), title, price:Number(price) }; items.push(it); res.status(201).json(it); });
app.listen(3000,()=>console.log('API on 3000'));
```
#### 참고 자료
- Express 공식 (https://expressjs.com/ko/) / HTTP 개요 (https://developer.mozilla.org/ko/docs/Web/HTTP/Overview)

## 9. Commit: feat(router): React Router 적용 및 페이지 분리 (선택)
- **뭘 배울까?**  URL 기반 화면 전환
- **왜 배우지?**  확장성과 UX
- **배운 내용과 연결해보자!**  토글→라우터→Next.js

#### 주요 학습 포인트
- RouterProvider, Link, Outlet
#### 예제 코드
```jsx
import {createBrowserRouter,RouterProvider,Link,Outlet} from 'react-router-dom';
function Layout(){return (<main><h1>중고마켓</h1><nav><Link to="/">목록</Link> <Link to="/new">등록</Link></nav><Outlet/></main>);}
const router=createBrowserRouter([{path:'/',element:<Layout/>,children:[{index:true,element:<Products/>},{path:'new',element:<NewItem/>}]}]);
export default function Root(){return <RouterProvider router={router}/>;}
```
#### 참고 자료
- React Router (https://reactrouter.com/en/main/start/overview)

## 10. Commit: feat(db): MongoDB Atlas 연동 및 상품 CRUD 기본 골격 (선택)
- **뭘 배울까?**  Mongoose 스키마/모델, Atlas 연결
- **왜 배우지?**  휘발성 → 영구 저장
- **배운 내용과 연결해보자!**  API↔DB 실제 서비스화

#### 주요 학습 포인트
- 연결 문자열, 스키마 정의, create/find
#### 예제 코드
```js
const mongoose=require('mongoose');
const Product=mongoose.model('Product',new mongoose.Schema({ title:String, price:Number },{ timestamps:true }));
async function main(){ await mongoose.connect(process.env.MONGO_URI,{ dbName:'day1' }); }
```
#### 참고 자료
- MongoDB Docs (https://www.mongodb.com/docs/)

## 11. Commit: feat(db): PostgreSQL + Prisma ORM 모델링 및 /posts 조회 예시 (선택)
- **뭘 배울까?**  Prisma 스키마/마이그레이션, 타입 안전 쿼리
- **왜 배우지?**  관계/무결성 중심 설계
- **배운 내용과 연결해보자!**  NoSQL ↔ RDB 비교

#### 주요 학습 포인트
- datasource/generator, 관계, Client 사용
#### 예제 코드
```prisma
datasource db { provider="postgresql"; url=env("DATABASE_URL") }
generator client { provider="prisma-client-js" }
model User { id Int @id @default(autoincrement()) email String @unique posts Post[] }
model Post { id Int @id @default(autoincrement()) title String author User @relation(fields:[authorId],references:[id]) authorId Int }
```
```js
const {PrismaClient}=require('@prisma/client'); const prisma=new PrismaClient();
app.get('/posts', async (req,res)=> res.json(await prisma.post.findMany({ include:{ author:true } })));
```
#### 참고 자료
- PostgreSQL 튜토리얼 (https://www.postgresql.org/docs/current/tutorial-start.html) / Prisma Docs (https://www.prisma.io/docs)
