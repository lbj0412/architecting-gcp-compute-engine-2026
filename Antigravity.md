# Google Cloud Course Modernization Guidelines (Antigravity v4.1.0 - 2026 Final Standard)

본 문서는 Google Cloud Authorized Trainer & Antigravity AI 시스템이 GCP 최신 교육 교안(2026 기준)을 컴파일하고 가공할 때 준수해야 하는 **7대 절대 철칙** 및 **1:1 페이지 완벽 매칭 수술 지침**을 정의합니다.

---

## 📌 7대 절대 철칙 (7 Unbreakable Directives)

1. **자동 빌드 전면 금지 (Single CLI Command Only)**:
   - 전체 모듈 자동 빌드를 절대 실행하지 않으며, 오직 사용자가 지정한 단 1개의 파일만 수동 CLI로 컴파일한다.

2. **원본 교안 1:1 완벽 페이지 매칭 & 내용 해석 수술 (Exact Page-by-Page Content Matching)**:
   - **원본 페이지 1:1 동기화**: 슬라이드 작성 시 원본 PDF 교안의 각 페이지(예: 4페이지 6대 컴퓨팅 비교표, 5페이지 IaaS 구조, 6페이지 7대 핵심 특징과 가용성 정책 등)와 내용/제목/구조를 100% 정밀 비교하여 정확하게 맞춘다.
   - **불릿 100% 보존 & 누락 0%**: PDF 파싱 시 생략되거나 뒤틀린 항목(예: 가용성 정책 - 라이브 마이그레이션 & 자동 다시 시작, 24시간 알맞은 추천, 초당 청구, SLA 없음 등)을 단 하나도 빠짐없이 100% 온전히 복원하고 자연스러운 발표문으로 수술한다.
   - **2026 최신 스펙 보강**: 원본 100% 보존 위에 Balanced PD, Hyperdisk, C3/C4/N4, A3 H100 GPU 최신 기술을 유기적으로 추가한다.

3. **표지 다크 네이비 / 본문 오프화이트 2계층 테마**:
   - 모듈 메인 표지: `linear-gradient(135deg, #0d1b2a 0%, #1b263b 50%, #1a73e8 100%)`
   - 본문 슬라이드: `#f8f9fa` 오프화이트 및 구글 4색 상단 액센트 바

4. **Clean Layout (상단/하단 텍스트 & 제목 밑줄 전면 제거)**:
   - 상단 헤더, 하단 슬라이드 번호/푸터 텍스트, `<h2>` 하단 파란 밑줄을 절대 생성하지 않는다.

5. **100% 좌측 정렬 (Strict Left Alignment)**:
   - 표지를 제외한 모든 본문 텍스트, 카드, 테이블 셀, 불릿 문장은 `text-align: left !important;`를 철저히 고수한다.

6. **레거시 3D PNG 아이콘 사용 & 워터마크 텍스트 전면 금지**:
   - 구글 공식 레거시 3D PNG 아이콘을 Base64 인라인 형태로 수직 배치한다.
   - 이미지 하단이나 히어로 박스에 `Module 03 Slide 05`와 같은 불필요한 장표 워터마크 텍스트를 절대 주입하지 않는다.

7. **표준 목차 리스트 & 단원 구분 타이틀 슬라이드 필수 배치**:
   - **목차(Agenda)**: 복잡한 카드 상자 대신 한눈에 들어오는 정갈한 세리프 인덱스 번호(`01`~`06`)와 수평 설명이 들어간 **'표준 목차 리스트(Clean Agenda List Layout)'**를 사용한다.
   - **단원 구분 타이틀 (Section Divider Cover)**: 대분류 단원이 새로 시작할 때마다 `SECTION 01`, 큼직한 `01` 인덱스, 단원 제목 및 개요 가이드 박스가 포함된 **'단원 구분 타이틀 페이지'**를 필수 배치한다.
   - **표(Table) 헤더 한 줄 정렬**: 비교표 작성 시 헤더 및 셀 항목 제목이 두 줄로 찌그러지지 않도록 `white-space: nowrap;` 및 패딩을 완벽히 맞춘다.

---

## 🛠️ 컴파일 및 검증 절차

```bash
# 1. HTML 컴파일
npx -y @marp-team/marp-cli --no-stdin --allow-local-files <target_file>.md -o slides_html/<target_file>_Slide.html

# 2. 16:9 PDF 내보내기
npx -y @marp-team/marp-cli --no-stdin --allow-local-files <target_file>.md --pdf -o slides_pdf/<target_file>_Slide.pdf
```
