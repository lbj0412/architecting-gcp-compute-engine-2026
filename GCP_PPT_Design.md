# Google Cloud Platform (GCP) 프레젠테이션 디자인 시스템

> **디자인 적용 대상**: Marp, Google Slides, HTML 웹 프레젠테이션 및 스티치 UI 컴포넌트
> **테마 명칭**: Google Cloud 엔터프라이즈 최종 승인 규격
> **폰트 패키지**: Pretendard v1.3.9 (웹 폰트 및 로컬 서체)
> **문서 버전**: 3.6.0 (Presenter View 프레임 차단 및 폴더 보관 필수 규격)

---

## 🎙️ 강사 대본 작성 근거 및 기준 (Script Baseline)

강사 대본(`<!-- comment: ... -->` 및 `lecturer_notes/*.html`) 작성 시 아래 3가지 소스를 100% 결합하여 작성합니다:

1. **원본 PDF 강사 노트 (1차 원천 데이터)**:
   - 학생용/강사용 교재 원본 PDF(`학생용/XX_Module_Name_KO (1).pdf`) 각 슬라이드 하단에 적힌 공식 텍스트 노트를 1차 기본 바탕으로 채택.
2. **베스핀글로벌 구글 MSP 엔지니어 페르소나**:
   - 베스핀글로벌 구글 MSP 팀 Cloud 엔지니어(2019~현재) 강사의 실무 페르소나 적용.
   - 단단하고 딱딱한 번역투 대신 자연스러운 구어체 대본(`~합니다`, `~입니다`, `~해 보세요`) 및 실무 경험 팁 주입.
3. **2026 개정 GCP 기술 및 실습 수칙**:
   - 최신 구글 클라우드 기술(GKE Autopilot Pod, Cloud Run v2, Terraform IaC, Gemini AI) 내용 갱신.
   - 베스핀 실습 환경(`bespin.email`/`KDT5T`, Service Account Key 보안 경고, VM OFF 수칙, 48시간 요금 시차) 멘트 보강.

---

## 🎨 1. 색상 시스템 (브랜드 컬러 팔레트)

### 주요 브랜드 색상 (Primary Brand Colors)
- **구글 블루 (Primary)**: `#1a73e8` / `rgb(26, 115, 232)`
- **구글 클라우드 다크 네이비 (표지 전용)**: `#0b3880` ~ `#1557bf`
- **보조 라이트 블루**: `#e8f0fe` / `rgb(232, 240, 254)`

### 보조 및 상태 색상 (Secondary & Status Colors)
- **구글 레드 (보안 경고 박스)**: `#ea4335` / 박스 배경 `#fce8e6`
- **구글 옐로우 (비용 관리 경고 박스)**: `#fbbc04` / 박스 배경 `#feefc3`
- **구글 그린 (완료/성공)**: `#34a853`

### 무채색 (Neutral Colors)
- **본문 다크 차콜**: `#202124`
- **보조 텍스트**: `#5f6368`
- **배경 라이트 그레이**: `#f8f9fa`
- **카드 배경 화이트**: `#ffffff`
- **테두리 경계선**: `#e8eaed`

---

## 🔤 2. 타이포그래피 및 용어 규격

### 서체 및 스타일 (Font Family & Styles)
- **기본 폰트**: `"Pretendard Variable"`, `Pretendard`, `-apple-system`, `BlinkMacSystemFont`, `sans-serif`
- **자간 설정**: `-0.02em` (가독성에 최적화된 서체 자간)
- **폰트 렌더링**: `-webkit-font-smoothing: antialiased`

### 필수 용어 준수 규칙 (Strict Terminology Rules)
1. **GKE Pod**: 한글 '팟' 표기 절대 금지 ➔ 영문 대소문자 혼용 **`GKE Pod`** 또는 **`Pod`**로 표기 통일.
2. **글로벌 전용 사설망**: 구교재 오역인 '글로벌 포화 네트워크' 표기 완전 금지 ➔ **`Google 글로벌 전용 사설망 (Global Private Network)`**으로 정확히 표기.
3. **기반 인프라**: 어색한 '하부 인프라' 대신 **`기반 인프라 (Underlying Infrastructure)`**로 표기.

---

## 📐 3. 슬라이드 레이아웃 및 컴포넌트 규격

### A. 표지 슬라이드 (`section.lead` 최종 표준)
- **배경색**: 다크 네이비 블루 그라데이션 `linear-gradient(135deg, #0b3880 0%, #1557bf 100%)`
- **상단 스트라이프**: 상단 6px 구글 4색 시그니처 배너 (`GCP Signature Stripe`)
- **100% 왼쪽 정렬 (`text-align: left`)**:
  - `Google Cloud` 공식 4색 심볼 브랜드 엠블럼 (`.cover-brand-header`)
  - 메인 타이틀 `h1` (`#ffffff`, `font-weight: 800`, `font-size: 50px`)
  - 서브타이틀 `h3` (`#e8f0fe`, `font-size: 22px`)
  - 하단 가이드 텍스트 박스 (`.cover-guide-box`, `background: rgba(255,255,255,0.15)`, `border-left: 4px solid #ffffff`)
- **고대비 백색 텍스트 규칙**: 파란 배경 위에서 어두운 회색/파란색 글자를 **완전히 배제**하고 100% 퓨어 화이트 (`#ffffff`) 및 라이트 블루 (`#e8f0fe`)로 지정.
- **우측 스플릿 그래픽 (`![bg right:42% fit](url)`)**: 우측 42% 영역에 독자적인 고화질 3D 테크/클라우드 비주얼 아트워크 배치.

### B. 슬라이드 애니메이션 및 Presenter View 버그 차단 규격
- **한 번에 즉시 노출 수칙**:
  - 클릭할 때마다 하나씩 나타나는 순차 노출(Fragment Animation) 금지 ➔ 모든 요소가 즉시 노출.
- **Presenter View 프레임 헛돎(`f=...`) 원천 차단 마크다운 규칙**:
  - Marp 마크다운 기본 불릿 (`*`, `-`) 대신 **HTML `<ul><li>...</li></ul>` 리스트 태그**를 사용하여 Marp 엔진이 Presenter View용 `f=...` 애니메이션 프레임을 0개도 생성하지 못하도록 조치.
- **자동 점프 & Fragment 소멸 JS 필수 주입**:
  - HTML 헤더에 `purgeFragmentHash()` 및 `ArrowRight`/`ArrowLeft` 슬라이드 점프 스크립트를 필수로 주입.

---

## 📂 4. 결과물 저장 폴더 및 파일 경로 엄격 규격 (Strict Directory Structure)

⚠️ **경고: 루트 디렉토리(`c:\Users\C\...`)에는 절대로 `XX_Slide.html` 파일이나 `XX_Lecturer_Notes.html` 파일이 존재하면 안 됩니다! (버그 유발 원천 차단)**

* **슬라이드 HTML 저장 경로**: **`slides_html/XX_Module_Name_Slide.html`** (단일 허용 경로)
* **강사 대본 HTML 저장 경로**: **`lecturer_notes/XX_Module_Name_Lecturer_Notes.html`** (단일 허용 경로)
* **슬라이드 원본 마크다운**: `XX_Module_Name_Marp.md`
* **현대화 개정 노트**: `XX_Module_Name_Modernized.md`
