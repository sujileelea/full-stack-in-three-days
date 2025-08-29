# Day 3 Summary — full-stack-in-three-days

## 📌 학습 범위
- Part A (21주차): TypeScript, 배포 및 테스트
- Part B (22–25주차는 고급 프로젝트라 생략)

## 🗂 Commit Index
- `feat(ts):` JavaScript → TypeScript 마이그레이션
- `feat(ts):` React/Express 타입 적용
- `feat(aws):` EC2 인스턴스 생성 및 배포
- `feat(aws):` S3/RDS 연동
- `chore(nginx):` Nginx 리버스 프록시 & PM2 설정
- `test(jest):` 기본 유닛 테스트 작성
- `test(jest):` 커버리지 분석 및 CI 통합
- `docs(day3):` Day3 학습 정리 문서화

## ▶ 실행 방법
### TypeScript 컴파일
```bash
cd backend
npx tsc
```

### 배포 (AWS)
- EC2, S3, RDS 설정 후 서버 실행
- Nginx + PM2로 안정성 확보

### 테스트
```bash
npm run test
```

## 📖 참고 문서
- [TypeScript 공식 문서](https://www.typescriptlang.org/docs/)
- [AWS EC2 시작하기](https://docs.aws.amazon.com/ec2/)
- [AWS S3 설명서](https://docs.aws.amazon.com/s3/)
- [AWS RDS 설명서](https://docs.aws.amazon.com/rds/)
- [Nginx Docs](https://nginx.org/en/docs/)
- [Jest 공식 문서](https://jestjs.io/docs/getting-started)
