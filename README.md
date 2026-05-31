# 외국인주민 프로그램 및 무료진료 수요조사

화성시외국인복지센터 설문조사 웹앱

## 접속 URL
https://centbro.github.io/hwaseong-survey/

## 기능
- 다국어 지원 (15개 언어)
- 설문조사 (10개 문항)
- 관리자 대시보드 (비밀번호: `hwaseong2025`)
- 응답 데이터 저장 (브라우저 localStorage)
- CSV 보내기
- 개별/전체 삭제

## 관리자 모드 접속
1. 우측 상단 "관리자 모드" 클릭
2. 비밀번호 입력: `hwaseong2025`
3. 대시보드에서 응답 확인 및 CSV보내기

## 로컬 테스트
```bash
# Python 내장 서버로 로컬 테스트
python -m http.server 8000
# 브라우저에서 http://localhost:8000 접속
```

## 배포 방법 (GitHub Pages)
1. 이 저장소를 로컬에 클론
2. `index.html` 수정 후 커밋
3. `git push origin main`
4. 자동 배포 (최대 10분 소요)

## 주의사항
- 데이터는 브라우저 localStorage에 저장됨
- 같은 기기/브라우저에서만 데이터 유지
- 캐시 삭제 시 데이터 초기화됨
- 서버 연동이 필요하면 Supabase/Firebase 연동 권장
