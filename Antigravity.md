# Google Cloud Architecture Training Modernization Standard (Antigravity v3.1.0)

본 문서는 Google Cloud 교육용 Marp 프레젠테이션 개정 및 자동 변환 시 준수해야 하는 **절대적 철칙과 가이드라인**입니다.

---

## ⚡ 1. 2026 Google Cloud 최신 기술 및 용어 검증 (2026 Modernization)
- **원문 100% 보존 & 최신화**: 교재 원문 텍스트의 제목과 내용을 100% 동일하게 유지하되, 구식 기술 표기나 레거시 사양은 **2026년 최신 Google Cloud 스펙 (Compute Engine C3/C3D/C4/N4, Hyperdisk, Spot VM, Gemini AI 연계 등)**으로 검증하고 최신 정보를 반영한다.
- **실습 환경 최신화**: 베스핀글로벌 전용 실습 환경(`KDT5T` 프로젝트, `bespin.email` 조직) 정보를 정확히 안내한다.

---

## 🚨 2. 자동 빌드 스크립트 실행 금지 수칙 (Strict Rule)
- `scratch/build_all_modules.py` 등 백그라운드 전체 자동 컴파일 스크립트는 **절대로 자동으로 실행하지 말 것**.
- 사용자가 직접 "전체 돌려라"라고 명시하기 전까지는, 오직 사용자가 작업 중인 **단 1개의 마크다운/HTML 슬라이드 파일만 수동 컴파일**할 것.

---

## 🎨 3. 표지 및 슬라이드 레이아웃 규칙 (Design Rules)

### A. 표지 (1페이지 & 마지막 Q&A 페이지)
- **배경**: 최초 다크 네이비 / 파란 고급 그라데이션 적용 (`linear-gradient(135deg, #0d1b2a 0%, #1b263b 50%, #1a73e8 100%)`)
- **텍스트/제목**: 원문의 제목, 서브타이틀, 문구 내용을 **100% 동일하게 유지** (내용 변경 절대 엄금)
- **로고**: 상단 좌측 구글 클라우드 공식 로고 배치 (Top 45px, Left 50px)
- **안내 박스**: 반투명 유광 유리 질감 (`background: rgba(255, 255, 255, 0.12); border: 1px solid rgba(255, 255, 255, 0.25);`)

### B. 헤더, 푸터, 제목 밑줄 금지 규칙 (Clean Layout)
- **상단 헤더 금지**: 불필요한 `Google Cloud | ...` 상단 헤더 텍스트 **전체 삭제 (`header: ''`)**
- **하단 푸터 금지**: 불필요한 `Architecting with...` 하단 푸터 텍스트 **전체 삭제 (`footer: ''`)**
- **제목 밑줄 금지**: H2 제목 하단의 파란색 조그만 밑줄(`h2::after`) **전체 삭제/미사용**

### C. 본문 텍스트 좌측 정렬 규칙 (Text Alignment)
- **좌측 정렬 필수**: 본문 내 모든 가이드 순서 목록(1, 2, 3...), 복습 퀴즈 보기(A, B, C, D...), 카드 텍스트, 설명 항목 등은 **무조건 좌측 정렬(`text-align: left;`)**을 적용할 것.
- 중앙 정렬은 표지 및 마지막 감사합니다(Q&A) 슬라이드만 제한적 허용.

### D. 이미지 및 아이콘 사용 규칙 (Icons & Screenshots)
- **외부 엉뚱한 풍경/자연 사진 사용 절대 금지**: Unsplash 등 연관 없는 풍경 사진을 슬라이드에 넣지 말 것.
- **구글 공식 레거시 아이콘 사용**: 컴퓨팅, 네트워크, 보안, 도구 소개 시 `google-cloud-legacy-icons/` 폴더 내의 구글 공식 PNG 아이콘을 **Base64 Data URI 형태로 직접 마크다운에 주입**하여 엑박(이미지 깨짐)을 100% 방지할 것.
- **실제 콘솔 스크린샷 캡처 적용**: 콘솔 실습 가이드 장표에는 사용자가 제공한 실제 GCP 콘솔 스크린샷 캡처 이미지를 우측 분할 배치(`![bg right:45% fit](data:image/png;base64,...)`)할 것.

---

## 🛠️ 4. 모듈별 파일 처리 절차
1. PDF 원본에서 텍스트와 이미지 100% 추출
2. 2026 최신 기술 및 스펙 검증 동기화
3. `XX_[Module_Name]_Marp.md` 마크다운 작성 (위의 Design Rules 준수)
4. Marp CLI로 단일 수동 빌드 (`slides_html/` 및 `slides_pdf/`)
5. GitHub Private 저장소 동기화 푸시 (`push_via_git.py`)
