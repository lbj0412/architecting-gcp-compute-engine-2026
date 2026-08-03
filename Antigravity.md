# Antigravity.md (v4.4.0 - GCP Course Modernizer & Official Docs Audit Standard)

본 문서는 Google Cloud Authorized Trainer & Presentation Designer 에이전트의 작업 지침 및 **GCP 공식 문서 실시간 교차 검증을 포함한 4대 정밀 검수 스킬 (v4.4.0)**을 다룹니다.

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

## 🔍 페이지 생성 후 4대 정밀 검수 스킬 (v4.4.0)

모든 슬라이드 작성 완료 후, 아래 4단계 검수 프로세스를 반드시 수행하여 원본과의 정밀 일치, GCP 공식 문서 검증 및 결함 여부를 확정한다:

1. **원본 PDF 1:1 내용 비교 검수 (Content Difference Audit)**
   - 원본 PDF 해당 페이지 텍스트/불릿 항목과 슬라이드 내용 간 다름 및 누락 0% 검증

2. **2026 최신화 항목 보강 검수 (2026 Spec Modernization Audit)**
   - Balanced PD, Hyperdisk, C3/C4/N4, A3 H100 GPU, Spot VM, OS Login 등 최신 구글 기술 반영 검증

3. **GCP 공식 문서 교차 검증 (GCP Official Docs Audit)**
   - 슬라이드 내 기술 설명, 용어, 제한 사항(Limits), 명령어가 구글 클라우드 공식 문서(`cloud.google.com/docs`) 스펙과 100% 정밀 일치하는지 실시간 검색/조회(`read_url_content` / `search_web`)하여 교차 검증

4. **이미지 깨짐 및 자산 결함 검수 (Image & Asset Rendering Audit)**
   - 브라우저 및 PDF 컴파일 상에서 이미지 경로 손상, 깨짐, 엑스박스, 워터마크 노출 전면 점검

---

## 🛠️ CLI 단일 컴파일 가이드

```bash
# HTML 컴파일
npx -y @marp-team/marp-cli --no-stdin --allow-local-files 03_Virtual_Machines_Marp.md -o slides_html/03_Virtual_Machines_Slide.html

# 16:9 PDF 컴파일
npx -y @marp-team/marp-cli --no-stdin --allow-local-files 03_Virtual_Machines_Marp.md --pdf -o slides_pdf/03_Virtual_Machines_Slide.pdf
```
