# 김비서 대시보드 프로젝트

**프리미엄 글래스모피즘 디자인의 업무 관리 웹 애플리케이션**

## 📋 목차

1. [프로젝트 개요](#프로젝트-개요)
2. [폴더 구조](#폴더-구조)
3. [주요 기능](#주요-기능)
4. [파일 설명](#파일-설명)
5. [기술 스택](#기술-스택)
6. [디자인 특징](#디자인-특징)
7. [개발 방법](#개발-방법)
8. [배포 방법](#배포-방법)
9. [주요 코드 패턴](#주요-코드-패턴)

---

## 프로젝트 개요

### 개념
마케팅팀의 업무를 효율적으로 관리하기 위한 웹 기반 대시보드 시스템입니다. 할 일 목록, 일정, 매출 분석, 회의록 등을 한 곳에서 관리할 수 있습니다.

### 주요 특징
- 🎨 **프리미엄 글래스모피즘 디자인**: 반투명 카드, 부드러운 블러, 섬세한 그림자
- 🌓 **다크/라이트 모드**: localStorage를 통한 자동 저장
- 📱 **완전 반응형**: 모바일, 태블릿, 데스크톱 모두 대응
- 📊 **다양한 시각화**: 차트, 다이어그램, 표 형식
- 🔄 **내비게이션**: 모든 페이지에서 쉬운 이동 가능

### 타깃 사용자
- 마케팅팀원
- 프로젝트 매니저
- 팀 리더

---

## 폴더 구조

```
수업/
├── index.html                    # 메인 페이지 (소개)
├── dashboard.html                # 핵심 대시보드 페이지
├── meeting-result.html           # 회의 결과 페이지
├── chart.html                    # 매출 분석 차트 페이지
├── diagram.svg                   # 업무 프로세스 다이어그램
├── report.html                   # 사이트 분석 리포트 (미완성)
├── .gitignore                    # Git 무시 규칙
├── .env.local                    # 환경 변수 (로컬, 커밋 제외)
├── .git/                         # Git 저장소
├── README.md                     # 이 문서
│
├── 김비서-데이터/                  # 데이터 폴더
│   ├── 매출데이터.csv
│   ├── 업무목록.csv
│   ├── 주간일정.txt
│   ├── 프로젝트현황.csv
│   └── 회의록.txt
│
└── 정리해줘/                      # 정리된 파일들
    ├── 보고서/                    # 보고서 문서들
    ├── 메모/                      # 메모 및 아이디어
    ├── 업무/                      # 업무 관련 파일
    └── 기타/                      # 기타 파일

```

---

## 주요 기능

### 1. 메인 페이지 (index.html)
- **목적**: 김비서 서비스 소개
- **구성요소**:
  - 큰 제목: "김비서를 소개합니다"
  - 한 줄 소개문
  - 3가지 주요 기능 카드
  - CTA 버튼: "내 대시보드 보기"
- **디자인**: 그라디언트 배경, 파스텔 색상 카드

### 2. 대시보드 (dashboard.html)
- **4개 섹션**:
  - ✅ **할 일 목록**: 우선순위별 색상 (빨강/주황/초록), 체크박스
  - 📅 **주간 일정**: 월~금 표 형식
  - 📈 **프로젝트 진행률**: 프로그레스 바 (4개 프로젝트)
  - 💰 **매출 요약**: 숫자 카드 (4가지 지표)
- **상단 네비게이션**: 5개 탭 메뉴 (현재 페이지 강조)

### 3. 회의록 (meeting-result.html)
- **3개 섹션**:
  - 📋 **회의 기본 정보**: 날짜, 참석자, 다음 회의 일정
  - 📝 **논의 내용 요약**: 4개 항목
  - ✓ **액션 아이템 표**: 담당자 | 할 일 | 기한
- **인쇄 기능**: 🖨️ 버튼으로 인쇄 가능

### 4. 매출 차트 (chart.html)
- **2개 차트** (HTML Canvas로 직접 그리기):
  - 📈 **월별 매출 추이**: 선 그래프 (1월, 2월 비교)
  - 📊 **제품별 매출 비교**: 막대 그래프 (6가지 제품)
- **숫자 포매팅**: ₩69,056,000 형식 (쉼표 포함)
- **통계**: 총 매출, 평균 거래액, 최고 판매 제품

### 5. 프로세스 다이어그램 (diagram.svg)
- **5단계 플로우**:
  1. 💡 기획 (파스텔 핑크)
  2. 🔨 제작 (파스텔 주황)
  3. 🔍 검토 (파스텔 노랑)
  4. 🚀 배포 (파스텔 초록)
  5. 📊 분석 (파스텔 파랑)
- **가로 화살표로 연결**, 둥근 사각형 박스

---

## 파일 설명

### index.html (약 150줄)
```
구조: HTML + CSS
- 메인 헤더 (제목, 소개)
- 3개 서비스 카드 (CSS Grid)
- CTA 버튼 (그라디언트)
- 테마 토글 스크립트
```

### dashboard.html (약 600줄)
```
구조: HTML + CSS + 간단한 JS
- 헤더 + 내비게이션 탭
- 4개 섹션 (CSS Grid 2x2)
- 각 섹션별 상세 스타일
- 테마 토글 스크립트
```

### meeting-result.html (약 580줄)
```
구조: HTML + CSS + 인쇄 스타일
- 헤더 + 내비게이션 탭
- 회의 정보 그리드
- 논의 내용 (텍스트)
- 액션 아이템 표 (table 태그)
- @media print 스타일
```

### chart.html (약 700줄)
```
구조: HTML + CSS + Canvas JS
- 헤더 + 내비게이션 탭
- 2개 Canvas 요소 (월별, 제품별)
- 차트 드로잉 함수 (JS)
- 데이터 구조 (배열)
- 레이아웃 재조정 리스너
```

### diagram.svg (약 50줄)
```
구조: SVG
- 5개 둥근 사각형 (rect + rx)
- 4개 화살표 (line + marker)
- 이모지 + 텍스트 (text 요소)
- 그림자 필터 (feDropShadow)
```

---

## 기술 스택

### 프론트엔드
- **마크업**: HTML5
- **스타일링**: CSS3 (Flexbox, Grid, Gradients)
- **상호작용**: Vanilla JavaScript (외부 라이브러리 없음)
- **그래픽**: HTML Canvas, SVG

### 특수 기술
- **글래스모피즘**: `backdrop-filter: blur()` + 반투명 배경
- **로컬 스토리지**: 테마 저장 (`localStorage.setItem()`)
- **반응형**: `@media (max-width: 768px)` 등
- **그라디언트**: `linear-gradient(135deg, #667eea 0%, #764ba2 100%)`
- **Canvas API**: `getContext('2d')`, `drawLine()`, `fillRect()` 등

### 데이터 소스
- **CSV 파일**: 매출, 업무 목록, 프로젝트 현황
- **TXT 파일**: 주간 일정, 회의록

---

## 디자인 특징

### 색상 팔레트

#### 라이트 모드
```
배경: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%)
텍스트: #1a1a1a
카드 배경: rgba(255, 255, 255, 0.7)
강조색: #667eea (파랑), #764ba2 (자주)
```

#### 다크 모드
```
배경: linear-gradient(135deg, #0f0f23 0%, #1a1a3e 100%)
텍스트: #e0e0e0
카드 배경: rgba(255, 255, 255, 0.05)
강조색: #a78bfa (라이트 보라), #f472b6 (핑크)
```

### 글래스모피즘 요소
```css
backdrop-filter: blur(10px);
background: rgba(255, 255, 255, 0.7);
border: 1px solid rgba(255, 255, 255, 0.5);
box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
```

### 타이포그래피
- **폰트**: `-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif`
- **제목**: 28-48px, font-weight 700
- **본문**: 14px, 줄 높이 1.6

### 애니메이션
- **호버 효과**: `transform: translateY(-4px)`, `box-shadow 강화`
- **탭 토글**: `transform: scale(1.1)`
- **전환**: `transition: all 0.3s ease`

---

## 개발 방법

### 초기 설정

#### 1단계: 프로젝트 폴더 생성
```bash
cd ~/Desktop
mkdir 수업
cd 수업
```

#### 2단계: 기본 파일 생성
```bash
# HTML 파일들 생성
touch index.html dashboard.html meeting-result.html chart.html

# 데이터 폴더 생성
mkdir 김비서-데이터
mkdir 정리해줘

# 환경 파일
touch .env.local
```

#### 3단계: .env.local 설정
```
GITHUB_TOKEN=your_token_here
```

### 페이지별 개발 순서

#### Phase 1: 기본 페이지 (index.html)
1. HTML 구조 작성 (header, cards, button)
2. CSS 작성 (그라디언트, 카드 레이아웃)
3. 테마 토글 스크립트 추가
4. localStorage 저장 기능

#### Phase 2: 대시보드 (dashboard.html)
1. HTML 구조 (4개 섹션)
2. CSS 그리드 레이아웃
3. 각 섹션 스타일 (카드, 테이블, 등)
4. 내비게이션 탭 추가
5. 테마 토글 적용

#### Phase 3: 회의록 (meeting-result.html)
1. HTML 구조 (정보, 요약, 표)
2. CSS 테이블 스타일
3. 인쇄 스타일 (@media print)
4. 내비게이션 탭 추가

#### Phase 4: 차트 (chart.html)
1. HTML Canvas 요소 준비
2. 데이터 구조 정의 (배열)
3. Chart 드로잉 함수 작성
4. 레이아웃 반응형 처리
5. 숫자 포매팅 함수

#### Phase 5: 다이어그램 (diagram.svg)
1. SVG 요소 배치 (rect, line, text)
2. 그림자, 화살표 마커 정의
3. 색상 적용
4. 구조 확인

#### Phase 6: 내비게이션 추가
1. CSS 스타일 작성 (.nav-tabs, .nav-tab, .nav-tab.active)
2. 각 페이지에 탭 HTML 추가
3. 현재 페이지 활성 상태 표시

### 데이터 준비

#### CSV 파일 형식 (매출데이터.csv)
```
날짜,제품,카테고리,수량,단가,매출액,지역
2026-01-05,무선 이어폰,전자기기,45,89000,4005000,서울
2026-01-05,보조배터리,전자기기,32,35000,1120000,서울
...
```

#### TXT 파일 형식 (주간일정.txt)
```
========================================
  2026년 3월 10일 ~ 14일 주간 일정
========================================

■ 월요일 (3/10)
- 10:00  마케팅팀 주간회의
- 14:00  신제품 런칭 킥오프 미팅
...
```

---

## 배포 방법

### 1단계: Git 초기화
```bash
cd ~/Desktop/수업

# Git 저장소 초기화
git init

# 사용자 정보 설정
git config user.email "parksangho1986@gmail.com"
git config user.name "Park Sangho"
```

### 2단계: .gitignore 생성
```bash
cat > .gitignore << 'EOF'
# 환경 변수
.env
.env.local
.env.*.local

# 노드 모듈
node_modules/
npm-debug.log*

# 운영 체제
.DS_Store
Thumbs.db

# IDE
.vscode/
.idea/

# 기타
token.txt
EOF
```

**중요**: `.env.local`과 `token.txt`는 **절대 커밋하지 말 것!**

### 3단계: 커밋 생성
```bash
# 모든 파일 스테이징 (.gitignore 제외)
git add .

# 커밋 메시지 (상세함)
git commit -m "Initial commit: Add dashboard, charts, meeting notes, and process diagram

- Dashboard with glassmorphism design and dark/light mode
- Sales analysis charts (monthly trend & product comparison)
- Meeting result page with action items
- Process workflow diagram (5 stages)
- Top navigation menu for all pages
- .gitignore for environment and sensitive files"
```

### 4단계: GitHub 푸시
```bash
# 원격 저장소 추가
git remote add origin https://github.com/anyoneanybody/class.git

# .env.local에서 토큰 읽어서 사용
TOKEN=$(cat .env.local | grep GITHUB_TOKEN | cut -d'=' -f2)
git remote remove origin
git remote add origin "https://${TOKEN}@github.com/anyoneanybody/class.git"

# 푸시
git push -u origin main
```

### 5단계: 로컬 서버 테스트 (선택사항)
```bash
# Python 내장 서버
python3 -m http.server 8000

# 브라우저에서 접속
http://localhost:8000
```

---

## 주요 코드 패턴

### 1. 테마 토글 패턴
```javascript
// HTML
<button class="toggle-btn" id="themeToggle">🌙</button>

// JavaScript
const themeToggle = document.getElementById('themeToggle');
const body = document.body;

// 저장된 테마 불러오기
const savedTheme = localStorage.getItem('theme') || 'light-mode';
body.className = savedTheme;

// 토글 이벤트
themeToggle.addEventListener('click', () => {
  if (body.classList.contains('light-mode')) {
    body.classList.remove('light-mode');
    body.classList.add('dark-mode');
    localStorage.setItem('theme', 'dark-mode');
  } else {
    body.classList.remove('dark-mode');
    body.classList.add('light-mode');
    localStorage.setItem('theme', 'light-mode');
  }
  updateToggleIcon();
});
```

### 2. 글래스모피즘 CSS
```css
.card {
  backdrop-filter: blur(10px);
  background: rgba(255, 255, 255, 0.7);
  border: 1px solid rgba(255, 255, 255, 0.5);
  border-radius: 20px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 48px rgba(0, 0, 0, 0.15);
}

/* 다크 모드 */
body.dark-mode .card {
  background: rgba(255, 255, 255, 0.05);
  border-color: rgba(255, 255, 255, 0.1);
}

body.dark-mode .card:hover {
  background: rgba(255, 255, 255, 0.08);
  box-shadow: 0 12px 48px rgba(102, 126, 234, 0.2);
}
```

### 3. 반응형 그리드
```css
.dashboard {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 30px;
}

@media (max-width: 1024px) {
  .dashboard {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 768px) {
  .dashboard {
    grid-template-columns: 1fr;
    gap: 20px;
  }
}
```

### 4. 숫자 포매팅
```javascript
function formatNumber(num) {
  return num.toLocaleString('ko-KR');
}

// 사용 예
console.log(formatNumber(69056000)); // "69,056,000"

// HTML에서
<div>₩{{ formatNumber(totalSales) }}</div>
```

### 5. Canvas 차트 기본 패턴
```javascript
function drawChart() {
  const canvas = document.getElementById('myChart');
  const ctx = canvas.getContext('2d');

  // 배경
  ctx.fillStyle = 'transparent';
  ctx.fillRect(0, 0, canvas.width, canvas.height);

  // 축 그리기
  ctx.strokeStyle = '#999';
  ctx.lineWidth = 2;
  ctx.beginPath();
  ctx.moveTo(50, 50);
  ctx.lineTo(50, canvas.height - 50);
  ctx.lineTo(canvas.width - 50, canvas.height - 50);
  ctx.stroke();

  // 데이터 시각화
  // ...
}
```

### 6. 내비게이션 탭 구조
```html
<!-- HTML -->
<div class="nav-tabs">
  <a href="dashboard.html" class="nav-tab active">📋 대시보드</a>
  <a href="meeting-result.html" class="nav-tab">📝 회의록</a>
  <a href="chart.html" class="nav-tab">📈 매출 현황</a>
  <a href="diagram.svg" class="nav-tab">🔄 업무 프로세스</a>
  <a href="report.html" class="nav-tab">📊 사이트 분석</a>
</div>

<!-- CSS -->
.nav-tab.active {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  box-shadow: 0 6px 20px rgba(102, 126, 234, 0.4);
}
```

---

## 다음 번 작업 체크리스트

- [ ] report.html 완성 (사이트 분석 리포트)
- [ ] 모바일 UI/UX 최적화
- [ ] 추가 데이터 시각화
- [ ] API 연동 (실시간 데이터)
- [ ] 데이터베이스 연결
- [ ] 사용자 인증 시스템
- [ ] 배포 (GitHub Pages 또는 웹 호스팅)

---

## 문제 해결 가이드

### 문제 1: 테마가 저장되지 않음
**원인**: localStorage가 비활성화됨
**해결**: 브라우저 개인정보 보호 설정 확인

### 문제 2: CSV 데이터가 안 보임
**원인**: 파일 경로 오류
**해결**: 경로가 상대 경로인지 확인 (예: `./kim.csv`)

### 문제 3: 차트가 안 그려짐
**원인**: Canvas가 지원되지 않음 또는 좌표 오류
**해결**: Canvas 좌표 계산 다시 확인

### 문제 4: GitHub 푸시 실패
**원인**: 토큰 만료 또는 권한 부족
**해결**: token.txt에서 새 토큰 생성 후 .env.local 업데이트

### 문제 5: 중문 파일명이 깨짐
**원인**: Git 한글 인코딩 설정
**해결**: `git config core.quotepath false` 실행

---

## 참고 자료

### 외부 라이브러리 없음!
이 프로젝트는 **HTML, CSS, Vanilla JavaScript만 사용**합니다. 추가 라이브러리가 필요 없습니다.

### 주요 학습 포인트
1. **CSS Grid & Flexbox**: 반응형 레이아웃
2. **backdrop-filter**: 글래스모피즘 효과
3. **Canvas API**: 동적 차트 그리기
4. **localStorage**: 클라이언트 저장소
5. **Git & GitHub**: 버전 관리 및 배포

---

## 라이선스

이 프로젝트는 개인 학습용입니다.

---

## 마지막 수정 날짜

2026년 5월 28일

---

**다음 번 작업 시 이 문서를 참고하세요! 🚀**
