# 언론이 또

https://again.misogynyx.com 웹사이트

[![Netlify Status](https://api.netlify.com/api/v1/badges/497bc07b-11d9-4eba-ab64-e13d902c6650/deploy-status)](https://app.netlify.com/sites/again-misogynyx/deploys)

## 데이터 흐름

1. https://github.com/misogynyx/news-crawler 에서 전체 뉴스 데이터를 수집하여
   S3에 업로드
2. https://github.com/misogynyx/done-it-again-analysis 에서는
   `news-crawler`에서 수집한 데잍처 중 최근 6개월 데이터만 받아서 분석하고
   그 결과를 다시 S3에 업로드
3. https://github.com/misogynyx/done-it-again 에서는 `done-it-again-analysis`의
   분석 결과를 S3에서 받아서 정적 웹사이트를 생성

## 개발하기

다음 명령을 실행한 후 http://localhost:8000/ 에 접속하세요.

```bash
./update.sh  # S3에서 분석 결과 데이터 받아오기
npm i  # NodeJS 패키지 설치
npm run develop  # 개발 서버 실행
```
