# Google Cloud Training Presentation Design System (v4.0.0)

본 문서는 Google Cloud 교육용 프레젠테이션, Marp 슬라이드, 강사 대본 교재 및 시각 자료의 디자인 일관성을 유지하기 위한 공식 스타일 가이드라인입니다.

---

## 1. Visual Theme & Style Concept

* **Concept**: Clean, Professional, Tech-Modern
* **Background**: 은은하고 밝은 라이트 그레이/화이트 그라데이션 (`linear-gradient(135deg, #ffffff 0%, #f8f9fa 100%)`)
* **Tone & Manner**: 신뢰감 있고 깔끔하며, 구글 고유의 4색(Blue, Red, Yellow, Green) 포인트를 활용한 현대적인 IT 교육 가이드 느낌

---

## 2. Color Palette

| 구분 | 색상 이름 | Hex Code | 용도 |
| :--- | :--- | :--- | :--- |
| **Primary Base** | Light Gray / White | `#F8F9FA` / `#FFFFFF` | 메인 배경색, 깔끔한 카드 배경 |
| **Primary Text** | Dark Charcoal | `#202124` | 메인 제목, 강한 강조 텍스트 |
| **Secondary Text**| Slate Gray | `#5F6368` | 부제목, 본문 텍스트, 하단 정보 |
| **Google Blue** | Primary Brand Color | `#4285F4` | 핵심 포인트 요소, 주요 라인 아트, 노드 |
| **Google Red** | Accent Color | `#EA4335` | 포인트 그래픽 도형 |
| **Google Yellow** | Accent Color | `#FBBC04` | 포인트 그래픽 도형 |
| **Google Green** | Accent Color | `#34A853` | 포인트 그래픽 도형 |

---

## 3. Typography & Hierarchy

* **Primary Font**: Pretendard v1.3.9, Google Sans, Noto Sans KR, or Inter (Sans-serif)
* **자간 설정**: `-0.02em` (가독성에 최적화된 자간)

| 요소 | 크기 (px/rem) | Weight | Color | 비고 |
| :--- | :--- | :--- | :--- | :--- |
| **Header Logo** | 24px (1.5rem) | Medium (500) | `#202124` | 좌측 상단 로고 조합 (Top 40px, Left 50px) |
| **Main Title (H1)** | 48px - 56px | Bold (700) | `#202124` | 중앙 타이틀 (줄바꿈 고려) |
| **Subtitle (H2)** | 28px - 32px | Medium (500) | `#202124` | 챕터 정보 및 상세 제목 |
| **Footer Text** | 14px (0.875rem) | Regular (400) | `#5F6368` | 우측 하단 문서 정보/연도 (Bottom 30px, Right 50px) |

---

## 4. Graphic Elements & Layout Rules

### 4.1. Layout Structure (표지 슬라이드 `section.lead`)
* **Top-Left**: Google Cloud 공식 로고 및 텍스트 조합 ( 여백: Top 40px, Left 50px )
* **Center**: 메인 타이틀(H1) 및 서브타이틀(H2/H3) 중앙 정렬
* **Bottom-Right**: 메타데이터 (예: `Google Cloud 교육 자료 | 2026 개정판`)
* **Background Decorative Elements**: 대각선 모서리에 수놓아지는 3D 클라우드 그래픽 및 구글 4색 데이터 노드 연결망

### 4.2. Decorative Graphics Style
1. **Cloud Graphics**:
   * 구글 브랜드 4색(Blue, Red, Yellow, Green)이 겹쳐진 형태의 부드러운 3D 구름 벡터 일러스트
   * 좌측 하단 및 우측 상단 모서리에 비대칭으로 배치하여 안정감 부여
2. **Data Node Network (Tech Graphic)**:
   * 얇은 다이아몬드/삼각형 와이어프레임 메시 (`#4285F4`, 투명도 60~80%)
   * 노드 연결점에 구글 컬러 원형 닷(Dot) 배치하여 IT/클라우드 연결성 표현
3. **Chapter Number Watermark**:
   * 배경 우측 중앙에 대형 라인아트 형태의 숫자 (예: `00`, `01`) 배치하여 챕터 직관성 강조

---

## 5. CSS / Styling Example (Reference)

```css
/* Container Layout (표지 슬라이드 lead) */
section.lead {
  width: 100%;
  height: 100vh;
  background: linear-gradient(135deg, #ffffff 0%, #f8f9fa 100%);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
  font-family: 'Pretendard Variable', 'Noto Sans KR', 'Google Sans', sans-serif;
  color: #202124;
  text-align: center !important;
  padding: 60px 80px;
  box-sizing: border-box;
}

/* 상단 4색 시그니처 배너 */
section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 6px;
  background: linear-gradient(90deg, #4285f4 0%, #4285f4 25%, #ea4335 25%, #ea4335 50%, #fbbc05 50%, #fbbc05 75%, #34a853 75%, #34a853 100%);
}

/* Typography Settings */
section.lead h1 {
  font-size: 52px;
  font-weight: 700;
  text-align: center !important;
  line-height: 1.3;
  color: #202124;
  margin-top: 20px;
  margin-bottom: 14px;
  letter-spacing: -0.03em;
}

section.lead h3 {
  font-size: 28px;
  font-weight: 500;
  text-align: center !important;
  color: #5f6368;
  margin-bottom: 24px;
  letter-spacing: -0.02em;
}

/* Header & Footer Position */
.header-logo {
  position: absolute;
  top: 40px;
  left: 50px;
  display: flex;
  align-items: center;
  gap: 12px;
}

.footer-info {
  position: absolute;
  bottom: 30px;
  right: 50px;
  font-size: 14px;
  color: #5f6368;
}
```

---

## 🎙️ 강사 대본 및 수칙 가이드

1. **대본 원천 출처**: `학생용/XX_Module_Name_KO (1).pdf` 하단 수록 노트를 1차 핵심 데이터로 수록.
2. **어조**: 베스핀글로벌 구글 MSP 엔지니어 강사 페르소나 구어체(`~합니다`, `~입니다`, `~해 보세요`).
3. **Presenter View 헛돎 방지**: Marp `*`, `-` 불릿 사용 금지 ➔ HTML `<ul><li>` 태그 사용 및 `purgeFragmentHash()` JS 주입.
4. **결과물 저장 폴더**:
   - 발표용 HTML: `slides_html/XX_Module_Name_Slide.html`
   - 단일 슬라이드 HTML: `slides_html_single/XX_Module_Name_Slide_XX.html`
   - 강사 대본 HTML: `lecturer_notes/XX_Module_Name_Lecturer_Notes.html`
