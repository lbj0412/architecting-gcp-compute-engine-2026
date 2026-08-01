# Google Cloud Presentation Design System (v6.1.0 - 2026 Light Theme Final Standard)

본 디자인 규격서는 Google Cloud Authorized Trainer 커리큘럼 발표 자료 컴파일 시 사용하는 표준 CSS 규칙, 레이아웃 스펙 및 **1:1 Exact Page Matching 수술 방법론**입니다.

---

## 🎨 Exact Page Matching Rules (v6.1.0)

1. **원본 PDF 페이지 1:1 완벽 구조 동기화**:
   - 슬라이드 생성 시 원본 교안의 각 페이지 번호(예: Page 4 비교표, Page 5 IaaS, Page 6 7대 특징 및 가용성 정책)와 슬라이드 내용을 100% 매칭시킨다.

2. **원문 불릿 100% 보존 & 누락 0% 규칙**:
   - 파싱 중 레이아웃 박스 분리로 생략되기 쉬운 항목(예: 가용성 정책 - 라이브 마이그레이션 & 자동 다시 시작, 24시간 알맞은 추천 엔진, 초당 청구, SLA 없음)을 단 하나도 놓치지 않고 1:1로 온전히 다 넣는다.

3. **워터마크 노출 금지**:
   - 이미지 및 히어로 박스 하단의 `Module 03 Slide 05`와 같은 불필요한 장표 워터마크 텍스트는 100% 전면 삭제한다.

4. **표 헤더 한 줄 정렬 (`white-space: nowrap;`)**:
   - 비교표 작성 시 헤더 및 항목 셀 제목이 두 줄로 일그러지지 않도록 한 줄 정렬을 고수한다.
