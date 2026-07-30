# Architecting with Google Compute Engine (2026 최신 개정판)

> **프로젝트 소개**: Google Cloud Compute Engine 아키텍팅 교육 과정 슬라이드, 1:1 강사 구어체 대본, Canva 연동 및 HTML 교재 통합 저장소
> **주관 및 운영**: 베스핀글로벌 구글 MSP 팀

---

## 📂 저장소 폴더 및 파일 구조

- 🖥️ **`slides_html/`**: 발표용 HTML 프레젠테이션 슬라이드 모음 (키보드 `P` 키로 발표자 대본 모드 지원)
- 📄 **`lecturer_notes/`**: 상단 PPT 슬라이드 + 하단 1:1 강사 구어체 대본 및 실무 팁 통합 HTML 교재
- 📄 **`slides_html_single/`**: 낱개 장표별로 개별 수정이 가능한 단일 HTML 슬라이드 모음
- 📄 **`slides_pdf/`**: Canva(캔바) 메인 [파일 가져오기]로 올렸을 때 글자가 100% 더블클릭 수정되는 16:9 PDF 파일 모음
- 🎨 **`GCP_PPT_Design.md`**: v3.7.0 Google Cloud 표준 프레젠테이션 디자인 가이드 문서
- 🤖 **`Antigravity.md`**: Google Antigravity AI 전용 표준 작업 지침 및 자동화 수칙
- 🎨 **`mcp.json` / `.vscode/mcp.json`**: Canva MCP 서버 연동 설정 파일
- ⚙️ **`gcp-course-modernizer` 스킬**: `C:\Users\C\.gemini\config\skills\gcp-course-modernizer\SKILL.md`

---

## 💡 주요 특징 및 준수 수칙

1. **Pretendard v1.3.9 폰트 & 100% 왼쪽 정렬 표지**:
   - 가독성이 뛰어난 Pretendard 서체 적용 및 다크 네이비 고대비 백색 텍스트 표지 표준 레이아웃 적용.
2. **1:1 강사 구어체 발표자 대본 탑재**:
   - `학생용/XX_Module_Name_KO (1).pdf` 하단 노트를 바탕으로 키보드 `P` 키 발표자 창의 `Presenter Notes` 란에 강사 대본 실시간 연동.
3. **Presenter View 헛돎 방지 수칙**:
   - Marp 마크다운 불릿 사용 금지 ➔ HTML `<ul><li>` 태그 적용 및 `purgeFragmentHash()` JS 스크립트 내장.
4. **실습 환경 및 보안/비용 규격**:
   - 베스핀글로벌 전용 GCP 프로젝트(`bespin.email` / `KDT5T`) 안내.
   - Service Account Key & API Key GitHub 노출 금지 경고 박스 및 VM OFF 48시간 요금 시차 수칙 수록.
