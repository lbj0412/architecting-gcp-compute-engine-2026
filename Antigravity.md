# Antigravity AI 프로젝트 지침 및 자동화 수칙

> **프로젝트 목표**: Architecting with Google Compute Engine 과정 개정 (모듈 00 ~ 11)
> **담당 AI**: Google Antigravity AI Pair Programmer
> **디자인 가이드 문서**: `GCP_PPT_Design.md` (v3.5.0)
> **지침 버전**: 1.3.0 (Presenter View 프레임 헛돎 방지 수칙 수록)

---

## 📌 프로젝트 개요 및 핵심 원칙
본 문서는 Google Antigravity AI가 구교재 GCP PDF 교재를 최신 2026 프레젠테이션 슬라이드, 1:1 강사 구어체 발표 대본, HTML 교재로 변환할 때 반복적인 질문 및 버그 없이 즉시 일관되게 수행하기 위한 **100% 한글 절대 준수 지침**입니다.

---

## 🛑 [필수] Presenter View 헛도는 버그(`f=...`) 원천 차단 수칙

Marp 슬라이드 변환 시 키보드 `P` 키 발표자 모드(Presenter View)에서 페이지가 안 넘어가고 헛도는 증상(`f=1, f=2...`)을 방지하기 위해 다음 규칙을 **100% 엄격히 준수**합니다:

1. **Marp 마크다운 불릿 리스트 구문 규칙**:
   - 마크다운 기본 불릿 (`* item` 또는 `- item`)은 Marp 파서가 Presenter View 전용 내부 프레임 인덱스(`f=...`)를 자동 생성하므로 **사용을 엄금**합니다.
   - 대신 **HTML 리스트 태그(`<ul><li>...</li></ul>`)** 또는 **CSS 카드/테이블 컴포넌트**를 사용하여 Marp 엔진이 `f=...` 애니메이션 프레임을 **단 1개도 생성하지 못하도록** 마크다운을 구성합니다.
2. **자동 점프 JS 스크립트 수술**:
   - 빌드된 HTML 파일(`slides_html/*.html`) 헤더에 `f=` 애니메이션 프레임을 실시간 파괴하고 오직 진짜 슬라이드 번호(`#1`, `#2`...)로 직접 점프하는 커스텀 JS 스크립트를 필수로 주입합니다.

---

## 🎙️ 강사 대본 작성 근거 및 기준 (Script Baseline)

강사 대본(`<!-- comment: ... -->` 및 `lecturer_notes/*.html`) 작성 시 아래 3가지 출처를 100% 결합하여 작성합니다:

1. **1차 원천 데이터 (원본 PDF 하단 강사 노트)**:
   - 학생용/강사용 교재 원본 PDF(`학생용/XX_Module_Name_KO (1).pdf`) 각 슬라이드 하단에 기재된 공식 텍스트 노트를 1차적인 핵심 근거 기준으로 추출·채택.
2. **강사 페르소나 및 구어체 어조**:
   - **페르소나**: 2019년부터 현재까지 베스핀글로벌 구글 MSP 팀에서 근무 중인 구글 클라우드 엔지니어 강사.
   - **어조**: 딱딱한 기계식 번역투를 완전히 제거하고, 실제 강의 현장에서 말하는 친근하고 명확한 **한국어 구어체 발표 대본**(`~합니다`, `~입니다`, `~해 보세요`)으로 구성.
3. **2026 최신 기술 & 실습 안내 멘트 결합**:
   - 2026년 최신 구글 클라우드 기술(GKE Autopilot Pod, Cloud Run v2, Terraform IaC, Gemini AI) 설명 반영.
   - 실제 베스핀글로벌 실습 환경(`bespin.email` / `KDT5T`), **Service Account Key & API Key 노출 엄금 경고**, **VM OFF 수칙**, **48시간 요금 시차 인지** 멘트를 각 슬라이드 대본에 필수 결합.

---

## 🛠️ 필수 용어 및 기술 표준 수칙

1. **절대 준수 용어 표기**:
   - **`GKE Pod`**: 한글 '팟' 표기 절대 금지 ➔ 영문 대소문자 **`GKE Pod`** 또는 **`Pod`**로 표기 통일.
   - **`Google 글로벌 전용 사설망`**: 구교재 오역인 '글로벌 포화 네트워크' 표기 완전 금지 ➔ **`Google 글로벌 전용 사설망 (Global Private Network)`**으로 표기.
   - **`기반 인프라`**: 어색한 '하부 인프라' 대신 **`기반 인프라 (Underlying Infrastructure)`**로 표기.

2. **2026 최신 GCP 기술 스택 반영**:
   - Compute Engine 커스텀 VM, GKE Autopilot Pod, Cloud Run v2, Terraform IaC, Vertex AI 및 Gemini AI 연동 반영.

---

## 🎨 슬라이드 디자인 시스템 규격 (`GCP_PPT_Design.md`)

1. **표지 슬라이드 (`section.lead`) 레이아웃**:
   - **100% 왼쪽 정렬 (`text-align: left !important`, `align-items: flex-start !important`)**.
   - **고대비 백색 텍스트**: 파란 다크 네이비 배경 위에서는 100% 퓨어 화이트 (`#ffffff`) 및 라이트 블루 (`#e8f0fe`) 글자만 사용.
   - Google Cloud 브랜드 엠블럼 (`.cover-brand-header`) + 반투명 글래스모피즘 가이드 박스 (`.cover-guide-box`).
   - 우측 42% 영역 전용 3D 테크 스플릿 비주얼 아트워크 배치 (`![bg right:42% fit](url)`).

2. **폰트 및 애니메이션**:
   - **서체**: `Pretendard v1.3.9` (-0.02em 자간 적용).
   - **한 번에 즉시 노출 수칙**: 클릭 순차 애니메이션 금지 (`* { animation: none !important; }`). 슬라이드를 넘기면 모든 요소가 즉시 100% 노출.

---

## 🛡️ 실습 환경, 보안 및 비용(FinOps) 수칙

1. **Qwiklabs 전면 삭제**: 퀵랩 내용 완전 제거 ➔ 베스핀글로벌 GCP 실습 프로젝트 적용:
   - **조직 (Organization)**: `bespin.email`
   - **프로젝트 (Project)**: `KDT5T`

2. **보안 경고 박스 (`.alert-danger-box`)**:
   - Service Account Key (`*.json`) 및 API Key를 Public망/GitHub 저장소에 절대 올리지 말라는 경고 박스 필수 배치.

3. **비용 관리 경고 박스 (`.alert-warning-box`)**:
   - 수업 마감 및 미사용 시 **가상 머신(VM) OFF 필수** 명시.
   - GCP 결제 데이터 집계 **최소 2일(48시간) 시차 인지** 경고 박스 필수 작성.

---

## 📄 강사 대본 및 결과물 저장 폴더 규격

1. **발표자 모드 대본 내장 (`<!-- comment: ... -->`)**:
   - Marp 슬라이드마다 1:1 강사 구어체 대본 주석 포함 ➔ 키보드 `P` 키 입력 시 발표자 모드 Presenter Notes 란에 실시간 동기화.

2. **결과물 저장 폴더 구조**:
   - 발표용 HTML 슬라이드: `slides_html/XX_Module_Name_Slide.html`
   - 강사 대본 HTML 교재: `lecturer_notes/XX_Module_Name_Lecturer_Notes.html`
   - 슬라이드 원본 마크다운: `XX_Module_Name_Marp.md`
   - 현대화 개정 노트: `XX_Module_Name_Modernized.md`
