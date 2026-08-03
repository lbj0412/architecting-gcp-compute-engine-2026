# Antigravity.md (v5.0.0 - GCP Course Modernizer & Lecturer Script Standard)

본 문서는 Google Cloud Authorized Trainer & Presentation Designer 에이전트의 작업 지침, **학생용 PDF 원본 대본 1:1 주입 규칙** 및 **GCP 공식 문서 교차 검증을 포함한 4대 정밀 검수 스킬 (v5.0.0)**을 다룹니다.

---

## 📌 8대 절대 철칙 (8 Unbreakable Directives)

1. **자동 빌드 금지 (Single CLI Command Execution Only)**
2. **원본 교안 1:1 완벽 페이지 매칭 & 내용 해석 수술 (Exact Page-by-Page Content & Layout Matching)**
3. **PDF 페이지별 원본 이미지 자동 전수 추출 & 1:1 주입 (Page-by-Page Auto Image Extraction)**
4. **표지 다크 테마 & 본문 화이트 테마 분리**
5. **Clean Layout (상단 헤더 / 하단 푸터 / 파란 밑줄 전면 제거)**
6. **100% 좌측 정렬 (Strict Left Alignment)**
7. **레거시 3D PNG 아이콘 & Base64 인라인 수직 배치 (워터마크 금지)**
8. **표준 목차 리스트 & 단원 구분 타이틀 슬라이드 필수 배치**

---

## 🎤 강사 발표문(Presenter Notes) 1:1 자동 주입 규칙

- `학생용/*.pdf` 원본 교재 하단 구글 공인 강사 낭독 대본(Student & Instructor Notes) 전수 추출.
- Marp 마크다운 1~N번 각 슬라이드 최하단 `<!-- comment: 💬 [강사 대본] "..." -->` 1:1 주입.
- 발표자 도구 (**`P` 키**) 입력 시 노상 창에 강사 대본 1:1 실시간표출 연동.
- Marp 헤더 영역에 의한 대본 1장 밀림 현상 예방 (Zero-Offset Slide Parsing).

---

## 🔍 페이지 생성 후 4대 정밀 검수 스킬 (v5.0.0)

1. **원본 PDF 1:1 내용 비교 검수 (Content Audit)**
2. **2026 최신화 항목 보강 검수 (2026 Spec Audit)**
3. **GCP 공식 문서 교차 검증 (GCP Official Docs Audit - `cloud.google.com/docs`)**
4. **이미지 깨짐 & 대본 오프셋 검수 (Image & Note Audit)**

---

## 🛠️ CLI 단일 컴파일 가이드

```bash
# HTML 컴파일 (P키 발표자 도구 연동)
npx -y @marp-team/marp-cli --no-stdin --allow-local-files 03_Virtual_Machines_Marp.md -o slides_html/03_Virtual_Machines_Slide.html

# 16:9 PDF 컴파일
npx -y @marp-team/marp-cli --no-stdin --allow-local-files 03_Virtual_Machines_Marp.md --pdf -o slides_pdf/03_Virtual_Machines_Slide.pdf
```
