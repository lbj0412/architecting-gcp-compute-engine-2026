# Google Cloud Presentation Design System (v6.0.0 - 2026 Light Theme Final Standard)

 본 디자인 규격서는 Google Cloud Authorized Trainer 커리큘럼 발표 자료 컴파일 시 사용하는 표준 CSS 규칙 및 레이아웃 스펙 시스템입니다.

---

## 🎨 Design System Specifications

### 1. Color Tokens
- **Lead Cover Background**: `linear-gradient(135deg, #0d1b2a 0%, #1b263b 50%, #1a73e8 100%)`
- **Body Background**: `#f8f9fa` (Off-White)
- **Primary Text**: `#202124` (Google Dark Gray)
- **Secondary Text**: `#5f6368` (Google Muted Gray)
- **Brand Primary Accent**: `#1a73e8` (Google Blue)
- **Brand Green Accent**: `#34a853` (Google Green)
- **Brand Red Accent**: `#ea4335` (Google Red)
- **Brand Yellow Accent**: `#fbbc05` (Google Yellow)
- **Google 4-Color Top Bar Gradient**: `linear-gradient(90deg, #4285f4 0%, #4285f4 25%, #ea4335 25%, #ea4335 50%, #fbbc05 50%, #fbbc05 75%, #34a853 75%, #34a853 100%)`

---

## 📐 Layout Components (v6.0.0)

### 1. Clean Agenda List Layout (표준 목차 리스트)
복잡한 카드 상자(`card-grid`) 대신, 정갈한 세리프 인덱스 번호와 일률적인 수평 설명 구성을 통해 가독성을 극대화한다.

```html
<div class="agenda-container">
  <div class="agenda-item">
    <span class="agenda-num">01</span>
    <span class="agenda-title">Compute Engine 옵션 & 머신 시리즈</span>
    <span class="agenda-desc">| VM 개념 및 2026 최신 C3/C4/N4/A3 머신 타입 사양</span>
  </div>
</div>
```

### 2. Section Divider Slide (단원 구분 타이틀 페이지)
새로운 대분류 학습 파트가 시작될 때마다 웅장하게 파트를 지목해 주는 표지 슬라이드.

```html
<!-- _class: section-divider -->
<div class="section-badge">SECTION 01</div>
<div class="section-num-large">01</div>
<div class="section-title-large">Compute Engine 옵션 & 머신 시리즈</div>
<div class="section-desc-box">학습 개요 가이드 설명 박스</div>
```

### 3. Single-line Table Header (한 줄 테이블 헤더)
테이블 헤더 및 셀 텍스트가 지저분하게 찌그러지지 않도록 `white-space: nowrap;` 및 패딩 맞춤 적용.

```css
table.comp-table th {
  background: #1a73e8;
  color: #ffffff;
  font-weight: 700;
  padding: 12px 10px;
  text-align: center;
  white-space: nowrap;
}
table.comp-table td.header-col {
  font-weight: 700;
  color: #1a73e8;
  background: #f8f9fa;
  white-space: nowrap;
  text-align: center !important;
}
```

---

## 🚫 Absolute Prohibition Rules (금지 사항)
- 전체 모듈 자동 빌드 스크립트 실행 전면 금지.
- 슬라이드 상단/하단 헤더/푸터 및 `<h2>` 파란 밑줄 주입 금지.
- 이미지 하단 및 히어로 박스 내 `Module 03 Slide 05`와 같은 불필요한 장표 워터마크 텍스트 노출 절대 금지.
- 원본 PDF 불릿 항목 생략 금지 (가용성 정책 - 라이브 마이그레이션 & 자동 다시 시작 포함 100% 보존).
