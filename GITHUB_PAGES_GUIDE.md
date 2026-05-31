# GitHub Pages 배포 완벽 가이드

## 저장소 정보
- 저장소: https://github.com/centbro/hwaseong-survey
- 배포 URL: https://centbro.github.io/hwaseong-survey/

## 방법 1: GitHub 웹사이트에서 직접 업로드 (추천 - Git 초보자용)

### 1단계: 파일 업로드
1. https://github.com/centbro/hwaseong-survey 접속
2. "Add file" → "Upload files" 클릭
3. `index.html` 파일 드래그앤드롭
4. "Commit changes" 클릭

### 2단계: GitHub Pages 활성화
1. 저장소 상단 "Settings" 탭 클릭
2. 왼쪽 사이드바에서 "Pages" 클릭
3. "Build and deployment" → "Source"에서 "Deploy from a branch" 선택
4. "Branch"에서 "main" 선택, "/ (root)" 선택
5. "Save" 클릭

### 3단계: 접속 확인
- 약 1~2분 후 https://centbro.github.io/hwaseong-survey/ 접속
- "Your site is live" 메시지 확인

---

## 방법 2: Git 명령어로 업로드 (개발자용)

### 사전 준비
```bash
# Git 설치 확인
git --version

# Git 설정 (최초 1회)
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

### 업로드 명령어
```bash
# 1. 저장소 클론
git clone https://github.com/centbro/hwaseong-survey.git
cd hwaseong-survey

# 2. 파일 복사 (index.html, README.md, .nojekyll)
#    → deploy_package 폴더의 파일들을 복사

# 3. 커밋 및 푸시
git add .
git commit -m "Initial survey deployment"
git push origin main
```

### GitHub Pages 설정
1. https://github.com/centbro/hwaseong-survey/settings/pages 접속
2. Source: "Deploy from a branch" → Branch: "main" → Save

---

## 방법 3: GitHub Desktop 사용 (GUI 선호자용)

1. https://desktop.github.com 다운로드 및 설치
2. "File" → "Clone repository" → URL 입력: `https://github.com/centbro/hwaseong-survey`
3. 로컬 폴더에 파일 복사
4. "Changes" 탭에서 커밋 메시지 입력 → "Commit to main"
5. "Push origin" 클릭

---

## 파일 구조
```
hwaseong-survey/
├── index.html      ← 메인 설문 파일 (필수)
├── README.md       ← 저장소 설명
├── .nojekyll       ← Jekyll 비활성화 (정적 HTML 보장)
└── .github/
    └── workflows/  ← (선택) CI/CD 자동화
```

---

## 업데이트 방법
수정 후 재배포:
```bash
git add .
git commit -m "Update survey"
git push origin main
```
자동으로 재배포됨 (최대 10분 소요)

---

## 문제 해결

### 페이지가 보이지 않음
- Settings → Pages에서 "Your site is live" 확인
- URL 대소문자 확인: `hwaseong-survey` (소문자)
- 브라우저 캐시 삭제 (Ctrl+Shift+R)

### 404 에러
- `index.html` 파일명 확인 (대문자 I, 소문자 html)
- 저장소 루트에 있는지 확인

### 한글 깨짐
- `index.html`이 UTF-8 인코딩인지 확인
- `<meta charset="UTF-8">` 태그 확인

---

## Supabase 서버 연동 (고급)
서버 저장이 필요하면 `survey_supabase.html` 참고:
1. https://supabase.com 가입
2. 프로젝트 생성 → SQL Editor에서 테이블 생성
3. API URL과 anon 키를 HTML에 입력
4. 배포
