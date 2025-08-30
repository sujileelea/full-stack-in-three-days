# Day3 Practice — TypeScript, AWS 배포, 테스트/CI

## 1. Commit: feat(ts): 백엔드 TypeScript 환경 초기 설정
- **뭘 배울까?**  TS 환경 구성
- **왜 배우지?**  타입 안정성으로 결함 예방
- **배운 내용과 연결해보자!**  JS → TS 전환 발판
#### 주요 학습 포인트
- tsconfig, ts-node/빌드, 타입 기초
#### 예제 코드
```bash
npm i -D typescript ts-node @types/node
npx tsc --init
```
#### 참고 자료
- TS Docs (https://www.typescriptlang.org/docs/)

## 2. Commit: feat(ts): Express 서버 TypeScript 마이그레이션 및 기본 타입 정의
- **뭘 배울까?**  요청/응답/미들웨어 타입
- **왜 배우지?**  API 계약 명시
- **배운 내용과 연결해보자!**  테스트 결합
#### 주요 학습 포인트
- @types/express, 타입 가드, zod(선택)
#### 예제 코드
```ts
import express, { Request, Response } from 'express';
const app = express();
app.get('/health', (req: Request, res: Response) => res.json({ ok: true }));
export default app;
```
#### 참고 자료
- Express (https://expressjs.com/ko/) / TS Docs (https://www.typescriptlang.org/docs/)

## 3. Commit: chore(aws): EC2 배포 준비 및 실행 순서 문서화
- **뭘 배울까?**  인스턴스 생성/보안그룹/배포 체크리스트
- **왜 배우지?**  실사용자에게 서비스 제공
- **배운 내용과 연결해보자!**  PM2/Nginx와 이어짐
#### 주요 학습 포인트
- SSH, Node 설치, env 설정
#### 예제 코드
```bash
ssh -i key.pem ubuntu@<ip>
sudo apt update && sudo apt install -y nodejs npm
```
#### 참고 자료
- AWS EC2 Guide (https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html)

## 4. Commit: chore(pm2): PM2 프로세스 설정 추가 및 빌드/실행 가이드
- **뭘 배울까?**  무중단 실행/재시작/로그
- **왜 배우지?**  운영 안정성
- **배운 내용과 연결해보자!**  Nginx 연계
#### 주요 학습 포인트
- pm2 start/monit/log, 에코시스템 파일
#### 예제 코드
```bash
npm i -g pm2
pm2 start "node dist/index.js" --name api
pm2 save && pm2 startup
```
#### 참고 자료
- PM2 Quick Start (https://pm2.keymetrics.io/docs/usage/quick-start/)

## 5. Commit: chore(nginx): Nginx 리버스 프록시 설정 예시와 적용 절차 문서화
- **뭘 배울까?**  프록시/SSL/도메인
- **왜 배우지?**  접근성·보안 향상
- **배운 내용과 연결해보자!**  테스트/CI로 안정화
#### 주요 학습 포인트
- server 블록, proxy_pass, gzip
#### 예제 코드
```nginx
server {
  listen 80;
  server_name example.com;
  location / { proxy_pass http://127.0.0.1:3000; }
}
```
#### 참고 자료
- Nginx Docs (https://nginx.org/en/docs/)

## 6. Commit: test(jest): Express 앱 모듈 분리 및 Supertest 기반 API 테스트 추가
- **뭘 배울까?**  단위/통합 테스트
- **왜 배우지?**  회귀 방지
- **배운 내용과 연결해보자!**  CI 연결
#### 주요 학습 포인트
- jest config, supertest 요청/검증
#### 예제 코드
```ts
import request from 'supertest';
import app from '../src/app';
test('GET /health', async () => {
  const r = await request(app).get('/health');
  expect(r.status).toBe(200);
  expect(r.body.ok).toBe(true);
});
```
#### 참고 자료
- Jest (https://jestjs.io/docs/getting-started) / Supertest (https://github.com/ladjs/supertest#readme)

## 7. Commit: ci: GitHub Actions로 백엔드 테스트 자동화 파이프라인 추가
- **뭘 배울까?**  워크플로 작성/캐시/병렬
- **왜 배우지?**  안정적 협업
- **배운 내용과 연결해보자!**  CD로 확장
#### 주요 학습 포인트
- node setup, npm ci, test job
#### 예제 코드
```yaml
name: ci
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: '20' }
      - run: npm ci
      - run: npm test --workspaces
```
#### 참고 자료
- GitHub Actions (https://docs.github.com/actions)
