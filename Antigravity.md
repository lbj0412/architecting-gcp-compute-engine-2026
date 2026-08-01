# Antigravity.md (v4.2.0 - GCP Course Modernizer & 3-Step Audit Standard)

본 문서는 Google Cloud Authorized Trainer & Presentation Designer 에이전트의 작업 지침 및 **페이지 생성 후 3대 정밀 검수 스킬 (v4.2.0)**을 다룹니다.

---

## 📌 7대 절대 철칙 (7 Unbreakable Directives)

1. **자동 빌드 금지 (Single CLI Command Execution Only)**
2. **원본 교안 1:1 완벽 페이지 매칭 & 내용 해석 수술 (Exact Page-by-Page Content & Layout Matching)**
3. **표지 다크 테마 & 본문 화이트 테마 분리**
4. **Clean Layout (상단 헤더 / 하단 푸터 / 파란 밑줄 전면 제거)**
5. **100% 좌측 정렬 (Strict Left Alignment)**
6. **레거시 3D PNG 아이콘 & Base64 인라인 수직 배치 (워터마크 금지)**
7. **표준 목차 리스트 & 단원 구분 타이틀 슬라이드 필수 배치**

---

## 🔍 페이지 생성 후 3대 정밀 검수 스킬 (v4.2.0)

모든 슬라이드 작성 완료 후, 아래 3단계 검수 프로세스를 반드시 수행하여 원본과의 정밀 일치 및 결함 여부를 확정한다:

1. **원본 PDF 1:1 내용 비교 검수 (Content Difference Audit)**
   - 원본 PDF 해당 페이지 텍스트/불릿 항목과 슬라이드 내용 간 다름 및 누락 0% 검증

2. **2026 최신화 항목 보강 검수 (2026 Spec Modernization Audit)**
   - Balanced PD, Hyperdisk, C3/C4/N4, A3 H100 GPU, Spot VM, OS Login 등 최신 구글 기술 반영 검증

3. **이미지 깨짐 및 자산 결함 검수 (Image & Asset Rendering Audit)**
   - 브라우저 및 PDF 컴파일 상에서 이미지 경로 손상, 깨짐, 엑스박스, 워터마크 노출 전면 점검

---

## 🛠️ CLI 단일 컴파일 가이드

```bash
# HTML 컴파일
npx -y @marp-team/marp-cli --no-stdin --allow-local-files 03_Virtual_Machines_Marp.md -o slides_html/03_Virtual_Machines_Slide.html

# 16:9 PDF 컴파일
npx -y @marp-team/marp-cli --no-stdin --allow-local-files 03_Virtual_Machines_Marp.md --pdf -o slides_pdf/03_Virtual_Machines_Slide.pdf
```

---

## Image Rendering Verification Addendum

이미지 태그가 존재하거나 `alt` 텍스트가 표시된다는 이유만으로 이미지를 정상으로 판정하지 않는다. HTML 및 PDF 렌더링 검수 시 다음 조건을 반드시 확인한다.

- 모든 `<img>` 요소의 `src` 속성이 존재하고 빈 값(`src`, `src=""`)이 아닌지 확인한다.
- 브라우저에서 각 이미지의 `img.complete === true`인지 확인한다.
- 각 이미지의 `img.naturalWidth > 0`인지 확인한다.
- 이미지 깨짐 아이콘, 대체 텍스트 단독 표시, 빈 이미지 박스가 없는지 시각적으로 확인한다.
- HTML 렌더링과 PDF 렌더링을 모두 검사한다. 한쪽에서만 정상이어도 최종 정상으로 판정하지 않는다.
- 페이지 구조에 `<img>` 태그가 있다는 사실만으로 정상 판정하지 않는다.
- 검수 범위의 모든 페이지를 실제 렌더링 상태로 확인하고, 문제가 발견되면 페이지 번호·이미지 `alt`·원인·검수 결과를 기록한다.
