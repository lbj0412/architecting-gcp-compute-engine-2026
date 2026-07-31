# Antigravity AI 프로젝트 지침 및 자동화 수칙 (v2.0.0)

> **프로젝트 목표**: Architecting with Google Compute Engine 과정 개정 (모듈 00 ~ 11)
> **담당 AI**: Google Antigravity AI Pair Programmer
> **디자인 가이드 문서**: `GCP_PPT_Design.md` (v4.0.0 - Clean Light Gray / White 4-Color Theme)
> **지침 버전**: 2.0.0 (새로운 라이트 그레이 4색 포인트 표지 테마 반영)

---

## 📌 프로젝트 개요 및 핵심 원칙
본 문서는 Google Antigravity AI가 구교재 GCP PDF 교재를 최신 2026 프레젠테이션 슬라이드, 1:1 강사 구어체 발표 대본, HTML 교재로 변환할 때 반복적인 질문 없이 즉시 수행하기 위한 **100% 한글 지침서**입니다.

---

## 🎨 새로운 표지 디자인 시스템 규격 (`GCP_PPT_Design.md` v4.0.0)

* **배경 (Background)**: 은은하고 깔끔한 라이트 그레이/화이트 그라데이션 (`linear-gradient(135deg, #ffffff 0%, #f8f9fa 100%)`)
* **메인 타이틀 (H1)**: 48px-56px Bold (700) 다크 차콜 (`#202124`), 중앙 정렬
* **서브타이틀 (H3)**: 28px-32px Medium (500) 슬레이트 그레이 (`#5F6368`), 중앙 정렬
* **좌측 상단 로고**: Top 40px, Left 50px 위치에 Google Cloud 공식 엠블럼과 텍스트 배치
* **우측 하단 메타데이터**: Bottom 30px, Right 50px 위치에 `Google Cloud 교육 자료 | 2026 개정판` 배치
* **포인트 그래픽**: 상단 6px 구글 4색 배너 + 3D 구름 벡터 일러스트 및 데이터 노드 와이어프레임 메시

---

## 🛑 [필수] Presenter View 헛돎 방지 & HTML 단일 경로 수칙

1. **저장 폴더 및 파일 경로 엄격 준수**:
   - 루트 디렉토리에 HTML 슬라이드 생성 금지!
   - 발표용 HTML: `slides_html/XX_Module_Name_Slide.html`
   - 단일 슬라이드 HTML: `slides_html_single/XX_Module_Name_Slide_XX.html`
   - 강사 대본 HTML: `lecturer_notes/XX_Module_Name_Lecturer_Notes.html`

2. **Marp 마크다운 불릿 리스트 구문 규칙**:
   - 마크다운 기본 불릿 (`* item` 또는 `- item`)은 Marp 파서가 Presenter View 전용 내부 프레임 인덱스(`f=...`)를 자동 생성하므로 **사용 엄금**.
   - 대신 **HTML 리스트 태그(`<ul><li>...</li></ul>`)** 또는 **CSS 카드/테이블 컴포넌트**를 사용.
3. **자동 점프 JS 필수 주입**:
   - `slides_html/*.html` 헤더에 `purgeFragmentHash()` 및 키보드 자동 점프 스크립트 필수 주입.

---

## 🎙️ 강사 대본 작성 출처 및 기준

1. **1차 원천 데이터**: `학생용/XX_Module_Name_KO (1).pdf` 하단 수록 구글 공식 노트 100% 채택.
2. **어조**: 베스핀글로벌 구글 MSP 팀 Cloud 엔지니어 강사 페르소나 구어체(`~합니다`, `~입니다`, `~해 보세요`).
3. **실습 및 보안/비용 규격**:
   - Qwiklabs 배제 ➔ 베스핀글로벌 GCP 실습 환경 (`bespin.email` / `KDT5T`).
   - Service Account Key & API Key 노출 엄금 경고 박스 및 VM OFF 48시간 요금 시차 인지 안내 결합.
