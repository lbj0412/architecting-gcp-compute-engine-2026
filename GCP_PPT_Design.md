# Google Cloud Presentation Design System (v5.0.0)

Google Cloud 교육용 프레젠테이션 디자인 일관성 및 정밀 레이아웃 가이드 문서입니다.

---

## 1. Visual Theme & Style Concept

* **Concept**: Clean, Professional, Tech-Modern, High-Readability
* **Cover Theme**: 프리미엄 다크 네이비 / 파란 그라데이션 (`linear-gradient(135deg, #0d1b2a 0%, #1b263b 50%, #1a73e8 100%)`)
* **Slide Theme**: 깔끔한 라이트 바탕 (`#f8f9fa` / `#ffffff`) + 구글 4색 포인트 배너 (상단 6px)

---

## 2. Text Alignment & Typography Rules (본문 좌측 정렬)

| 구 분 | 정렬 방식 | 상세 규칙 |
| :--- | :--- | :--- |
| **표지 / Q&A** | 중앙 정렬 (`text-align: center`) | H1 메인 타이틀, 서브타이틀, 안내 박스 |
| **본문 가이드** | **좌측 정렬 (`text-align: left`)** | 1, 2, 3... 순서 번호 가이드 목록 |
| **퀴즈 보기** | **좌측 정렬 (`text-align: left`)** | A, B, C, D... 복습 퀴즈 선택 항목 |
| **카드 / 리스트** | **좌측 정렬 (`text-align: left`)** | 일반 설명문, 불릿 항목, 카드 박스 내부 문구 |

---

## 3. Header, Footer & Underline Elimination Rules

1. **상단 Header 미사용 (`header: ''`)**: 불필요한 상단 브랜드 텍스트 제거
2. **하단 Footer 미사용 (`footer: ''`)**: 불필요한 하단 저작권 텍스트 제거
3. **H2 파란 밑줄 미사용 (`h2::after` 제거)**: 제목 아래의 가로선 제거로 가독성 극대화

---

## 4. Official Legacy Icon System (`google-cloud-legacy-icons`)

* 연관 없는 외부 자연/풍경 사진 사용 엄금.
* 서비스 소개 시 `google-cloud-legacy-icons/` 폴더 내의 구글 공식 PNG 아이콘을 **Base64 Data URI 형태로 직접 인라인 주입**하여 엑박 방지.
* 콘솔 실습 가이드 장표는 사용자의 실제 GCP 콘솔 스크린샷 캡처 화면을 우측 분할 배치.
