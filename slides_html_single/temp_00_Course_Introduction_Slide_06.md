---
marp: true
theme: uncover
paginate: true
header: 'Google Cloud | 구글 클라우드 아키텍처 과정'
footer: 'Architecting with Google Compute Engine © 2026 개정판'
style: |
  @import url("https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.css");
  
  /* 클릭 순차 애니메이션 완전 무효화 -> 모든 요소 한 번에 노출 */
  * {
    animation: none !important;
    transition: none !important;
  }
  section *, section ul, section li, section div, section p {
    opacity: 1 !important;
    visibility: visible !important;
  }

  /* 전반적인 슬라이드 기본 설정 (Pretendard v1.3.9 폰트 적용) */
  section {
    font-family: "Pretendard Variable", Pretendard, -apple-system, BlinkMacSystemFont, system-ui, Roboto, "Helvetica Neue", "Segoe UI", "Apple SD Gothic Neo", "Noto Sans KR", "Malgun Gothic", "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    background: #f8f9fa;
    color: #202124;
    padding: 70px 80px 50px 80px;
    font-size: 24px;
    line-height: 1.5;
    letter-spacing: -0.02em;
    box-sizing: border-box;
  }
  
  /* 구글 상단 4색 브랜드 포인트 라인 (GCP Signature Stripe) */
  section::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 6px;
    background: linear-gradient(90deg, #4285f4 0%, #4285f4 25%, #ea4335 25%, #ea4335 50%, #fbbc05 50%, #fbbc05 75%, #34a853 75%, #34a853 100%);
  }

  /* 헤더 & 푸터 */
  header {
    font-family: "Pretendard Variable", Pretendard, sans-serif;
    font-size: 13px;
    font-weight: 700;
    color: #1a73e8;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    top: 24px;
    left: 80px;
  }
  footer {
    font-family: "Pretendard Variable", Pretendard, sans-serif;
    font-size: 12px;
    color: #70757a;
    bottom: 20px;
    left: 80px;
  }
  
  /* 01. 표지 타이틀 슬라이드 (Google Cloud Training Presentation Design System v4.0.0) */
  section.lead {
    background: linear-gradient(135deg, #ffffff 0%, #f8f9fa 100%);
    color: #202124;
    padding: 80px 80px;
    text-align: center !important;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center !important;
    position: relative;
  }
  section.lead header {
    display: none;
  }
  section.lead footer {
    display: none;
  }

  /* 상단 좌측 로고 조립 (Top 40px, Left 50px) */
  .cover-header-logo {
    position: absolute;
    top: 40px;
    left: 50px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .cover-header-text {
    font-size: 24px;
    font-weight: 600;
    color: #202124;
    letter-spacing: -0.02em;
  }

  /* 중앙 타이틀 (H1) 및 서브타이틀 (H3) */
  section.lead h1 {
    color: #202124;
    font-size: 52px;
    font-weight: 700;
    line-height: 1.3;
    margin-top: 15px;
    margin-bottom: 12px;
    letter-spacing: -0.03em;
    text-align: center !important;
  }
  section.lead h3 {
    color: #5f6368;
    font-size: 28px;
    font-weight: 500;
    margin-bottom: 20px;
    letter-spacing: -0.02em;
    text-align: center !important;
  }

  .cover-guide-box {
    background: #ffffff;
    border: 1px solid #e8eaed;
    border-radius: 12px;
    padding: 14px 28px;
    color: #3c4043 !important;
    font-size: 19px;
    font-weight: 600;
    margin-top: 10px;
    box-shadow: 0 4px 16px rgba(60, 64, 67, 0.08);
    text-align: center !important;
  }

  /* 우측 하단 메타데이터 (Bottom 30px, Right 50px) */
  .cover-footer-info {
    position: absolute;
    bottom: 30px;
    right: 50px;
    font-size: 14px;
    color: #5f6368;
    font-weight: 500;
  }

  /* 일반 슬라이드 제목 (H1 & H2) */
  h1, h2 {
    color: #1a73e8;
    font-size: 38px;
    font-weight: 800;
    margin-top: 0;
    margin-bottom: 24px;
    letter-spacing: -0.03em;
  }
  
  h2::after {
    content: '';
    display: block;
    width: 50px;
    height: 4px;
    background: #1a73e8;
    margin-top: 8px;
    border-radius: 2px;
  }

  /* 구글 전용 HTML 불릿 리스트 */
  ul {
    list-style: none;
    padding-left: 0;
    margin-top: 0;
  }
  li {
    position: relative;
    padding-left: 30px;
    margin-bottom: 14px;
    font-weight: 500;
    letter-spacing: -0.02em;
    font-size: 21px;
  }
  li::before {
    content: '';
    position: absolute;
    left: 4px;
    top: 12px;
    width: 8px;
    height: 8px;
    background-color: #1a73e8;
    border-radius: 50%;
  }

  /* 강사 프로필 전용 한눈에 보이는 리스트 테이블 박스 */
  .profile-container {
    background: #ffffff;
    border-radius: 16px;
    padding: 26px 32px;
    box-shadow: 0 4px 20px rgba(60, 64, 67, 0.08);
    border: 1px solid #e8eaed;
    border-left: 6px solid #1a73e8;
    margin-top: 10px;
  }
  .profile-row {
    display: flex;
    align-items: center;
    padding: 10px 0;
    border-bottom: 1px solid #f1f3f4;
    font-size: 20px;
  }
  .profile-row:last-child {
    border-bottom: none;
  }
  .profile-period {
    font-weight: 700;
    color: #1a73e8;
    min-width: 170px;
    letter-spacing: -0.01em;
  }
  .profile-detail {
    color: #3c4043;
    font-weight: 500;
  }

  /* 카드 컴포넌트 */
  .card-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-top: 10px;
  }
  .card-grid-3 {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 16px;
    margin-top: 10px;
  }
  .card {
    background: #ffffff;
    border-radius: 14px;
    padding: 20px 24px;
    box-shadow: 0 4px 20px rgba(60, 64, 67, 0.08);
    border: 1px solid #e8eaed;
  }
  .card-title {
    font-size: 19px;
    font-weight: 700;
    color: #1a73e8;
    margin-bottom: 6px;
    letter-spacing: -0.02em;
  }
  .card-desc {
    font-size: 16px;
    font-weight: 400;
    color: #5f6368;
    line-height: 1.5;
  }

  /* 17페이지 학습 로드맵 전용 스텝 레이아웃 */
  .roadmap-layout {
    display: grid;
    grid-template-columns: 1fr 1.3fr;
    gap: 20px;
    margin-top: 15px;
  }
  .roadmap-info-box {
    background: #ffffff;
    border-radius: 14px;
    padding: 24px;
    box-shadow: 0 4px 20px rgba(60, 64, 67, 0.08);
    border: 1px solid #e8eaed;
  }
  .roadmap-steps-container {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }
  .roadmap-step-item {
    background: #ffffff;
    border-radius: 12px;
    padding: 16px 20px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.05);
    border: 1px solid #e8eaed;
    display: flex;
    align-items: center;
    gap: 16px;
  }
  .roadmap-step-active {
    border: 2px solid #1a73e8;
    background: #e8f0fe;
  }
  .step-num {
    background: #dadce0;
    color: #3c4043;
    font-weight: 800;
    width: 38px;
    height: 38px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 18px;
    flex-shrink: 0;
  }
  .roadmap-step-active .step-num {
    background: #1a73e8;
    color: #ffffff;
  }
  .step-text {
    font-size: 17px;
    font-weight: 700;
    color: #202124;
    line-height: 1.3;
  }

  /* 보안 경고 박스 */
  .alert-danger-box {
    background: #fce8e6;
    border-left: 6px solid #ea4335;
    border-radius: 12px;
    padding: 20px 24px;
    margin-top: 15px;
  }
  .alert-danger-title {
    color: #c5221f;
    font-size: 20px;
    font-weight: 800;
    margin-bottom: 8px;
  }

  .alert-warning-box {
    background: #feefc3;
    border-left: 6px solid #fbbc04;
    border-radius: 12px;
    padding: 20px 24px;
    margin-top: 15px;
  }
  .alert-warning-title {
    color: #b06000;
    font-size: 20px;
    font-weight: 800;
    margin-bottom: 8px;
  }

  /* 표(Table) 스타일링 */
  table {
    width: 100%;
    border-collapse: separate;
    border-spacing: 0;
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 4px 16px rgba(0, 0, 0, 0.06);
    background: #ffffff;
    font-size: 18px;
    margin-top: 15px;
  }
  th {
    background: #1a73e8;
    color: #ffffff;
    font-weight: 700;
    padding: 12px 16px;
    text-align: left;
  }
  td {
    padding: 12px 16px;
    border-bottom: 1px solid #e8eaed;
    color: #3c4043;
  }
  tr:last-child td { border-bottom: none; }
  tr:nth-child(even) { background-color: #f8f9fa; }
  
  section:not(.lead) img {
    border-radius: 14px;
    box-shadow: 0 8px 24px rgba(60, 64, 67, 0.15);
  }
  
  .badge {
    display: inline-block;
    padding: 6px 14px;
    border-radius: 20px;
    font-size: 13px;
    font-weight: 800;
    background: #e8f0fe;
    color: #1a73e8;
    margin-bottom: 14px;
    letter-spacing: 0.5px;
  }
---

<!-- Page 6 -->

## 글로벌 인프라 (Region, PoP, Network)

![bg right:48% fit](images/gcp_region_map.png)

<ul>
  <li><strong>리전 (Region)</strong>: 전 세계 40개 이상 (서울 asia-northeast3 등)</li>
  <li><strong>영역 (Zone)</strong>: 리전당 최소 3개 이상의 독립 고가용성 존</li>
  <li><strong>에지 접속 지점 (PoP)</strong>: 지구를 둘러싼 Google 전용 고속 광케이블 네트워크</li>
</ul>

<!--
comment:
💬 [강사 대본]
"이 지도가 바로 Google Cloud의 글로벌 인프라 지도입니다. 서울 리전을 비롯해 40개 이상의 리전이 존재하며, 각 리전은 최소 3개의 독립된 존(Zone)으로 구성되어 완벽한 고가용성을 제공합니다."
-->
