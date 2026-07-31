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
    z-index: 10;
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
  
  /* 01. 표지 타이틀 슬라이드 (3D Cloud SVG Background) */
  section.lead {
    background-image: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxOTIwIDEwODAiIHdpZHRoPSIxOTIwIiBoZWlnaHQ9IjEwODAiPg0KICA8ZGVmcz4NCiAgICA8bGluZWFyR3JhZGllbnQgaWQ9ImJnLWdyYWQiIHgxPSIwJSIgeTE9IjAlIiB4Mj0iMTAwJSIgeTI9IjEwMCUiPg0KICAgICAgPHN0b3Agb2Zmc2V0PSIwJSIgc3RvcC1jb2xvcj0iI2ZmZmZmZiIvPg0KICAgICAgPHN0b3Agb2Zmc2V0PSIxMDAlIiBzdG9wLWNvbG9yPSIjZjhmOWZhIi8+DQogICAgPC9saW5lYXJHcmFkaWVudD4NCiAgICA8ZmlsdGVyIGlkPSJzaGFkb3ciIHg9Ii0xMCUiIHk9Ii0xMCUiIHdpZHRoPSIxMjAlIiBoZWlnaHQ9IjEyMCUiPg0KICAgICAgPGZlRHJvcFNoYWRvdyBkeD0iMCIgZHk9IjgiIHN0ZERldmlhdGlvbj0iMTIiIGZsb29kLW9wYWNpdHk9IjAuMSIgZmxvb2QtY29sb3I9IiMyMDIxMjQiLz4NCiAgICA8L2ZpbHRlcj4NCiAgPC9kZWZzPg0KDQogIDwhLS0gQmFja2dyb3VuZCBCYXNlIC0tPg0KICA8cmVjdCB3aWR0aD0iMTkyMCIgaGVpZ2h0PSIxMDgwIiBmaWxsPSJ1cmwoI2JnLWdyYWQpIi8+DQoNCiAgPCEtLSBUb3AgUmlnaHQgM0QgQ2xvdWQgJiBOb2RlIE5ldHdvcmsgR3JvdXAgLS0+DQogIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDExODAsIC0zMCkiPg0KICAgIDwhLS0gTGlnaHQgQmx1ZSBPdXRlciBDbG91ZCAtLT4NCiAgICA8cGF0aCBkPSJNMTUwIDI1MCBDMTUwIDE3MCwgMjQwIDEyMCwgMzIwIDE1MCBDMzcwIDgwLCA0ODAgODAsIDUzMCAxNTAgQzYxMCAxMzAsIDY5MCAxOTAsIDY3MCAyNzAgQzcyMCAzMzAsIDY3MCA0MjAsIDU4MCA0MjAgTDE1MCA0MjAgWiIgZmlsbD0iI2QyZTNmYyIgb3BhY2l0eT0iMC44NSIvPg0KICAgIDwhLS0gR3JlZW4gQ2xvdWQgLS0+DQogICAgPHBhdGggZD0iTTQwIDI0MCBDNDAgMTYwLCAxMjAgMTEwLCAyMDAgMTQwIEMyNDAgODAsIDM0MCA4MCwgMzgwIDE0MCBDNDQwIDEyMCwgNTEwIDE3MCwgNDkwIDI0MCBMNDAgMjQwIFoiIGZpbGw9IiMzNGE4NTMiIG9wYWNpdHk9IjAuOSIvPg0KICAgIDwhLS0gV2hpdGUgRnJvbnQgT3ZlcmxheSBDbG91ZCAtLT4NCiAgICA8cGF0aCBkPSJNMjAwIDIwMCBDMjAwIDE0MCwgMjcwIDEwMCwgMzQwIDEzMCBDMzgwIDgwLCA0NzAgODAsIDUxMCAxMzAgQzU2MCAxMTAsIDYzMCAxNjAsIDYwMCAyMjAgQzY0MCAyNzAsIDYwMCAzNDAsIDUyMCAzNDAgTDIwMCAzNDAgWiIgZmlsbD0iI2ZmZmZmZiIgb3BhY2l0eT0iMC45NSIgZmlsdGVyPSJ1cmwoI3NoYWRvdykiLz4NCiAgICANCiAgICA8IS0tIFRvcCBSaWdodCBOb2RlIE5ldHdvcmsgV2lyZWZyYW1lIC0tPg0KICAgIDxnIHN0cm9rZT0iIzQyODVmNCIgc3Ryb2tlLXdpZHRoPSIyLjUiIG9wYWNpdHk9IjAuNyIgZmlsbD0ibm9uZSI+DQogICAgICA8bGluZSB4MT0iNDIwIiB5MT0iMTMwIiB4Mj0iNTYwIiB5Mj0iNTAiIC8+DQogICAgICA8bGluZSB4MT0iNTYwIiB5MT0iNTAiIHgyPSI2NDAiIHkyPSIxNTAiIC8+DQogICAgICA8bGluZSB4MT0iNjQwIiB5MT0iMTUwIiB4Mj0iNDgwIiB5Mj0iMjAwIiAvPg0KICAgICAgPGxpbmUgeDE9IjU2MCIgeTE9IjUwIiB4Mj0iNzIwIiB5Mj0iMjIwIiAvPg0KICAgIDwvZz4NCiAgICA8Y2lyY2xlIGN4PSI1NjAiIGN5PSI1MCIgcj0iMTMiIGZpbGw9IiM0Mjg1ZjQiLz4NCiAgICA8Y2lyY2xlIGN4PSI2NDAiIGN5PSIxNTAiIHI9IjExIiBmaWxsPSIjMzRhODUzIi8+DQogICAgPGNpcmNsZSBjeD0iNzIwIiBjeT0iMjIwIiByPSIxNCIgZmlsbD0iI2VhNDMzNSIvPg0KICA8L2c+DQoNCiAgPCEtLSBCb3R0b20gTGVmdCAzRCBDbG91ZCAmIE5vZGUgR3JvdXAgLS0+DQogIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKC0xMDAsIDUyMCkiPg0KICAgIDwhLS0gQmlnIEJsdWUgU2hhcGUgQmFja2dyb3VuZCAtLT4NCiAgICA8cGF0aCBkPSJNMCAyMjAgQzYwIDkwLCAyMDAgNjAsIDI4MCAxNzAgQzM2MCA5MCwgNDcwIDEzMCwgNDUwIDI1MCBMMCA1NTAgWiIgZmlsbD0iIzQyODVmNCIgb3BhY2l0eT0iMC44NSIvPg0KICAgIDwhLS0gTGlnaHQgQmx1ZS9XaGl0ZSBDbG91ZCAtLT4NCiAgICA8cGF0aCBkPSJNODAgMjgwIEM4MCAxOTAsIDE3MCAxNDAsIDI1MCAxODAgQzMxMCAxMTAsIDQyMCAxMjAsIDQ2MCAxOTAgQzUzMCAxODAsIDU5MCAyNDAsIDU2MCAzMjAgTDgwIDMyMCBaIiBmaWxsPSIjZThmMGZlIiBvcGFjaXR5PSIwLjkiLz4NCiAgICA8IS0tIFllbGxvdyAzRCBGcm9udCBDbG91ZCAtLT4NCiAgICA8cGF0aCBkPSJNMTYwIDM0MCBDMTYwIDI0MCwgMjYwIDE5MCwgMzQwIDI0MCBDNDAwIDE3MCwgNTEwIDE4MCwgNTUwIDI2MCBDNjEwIDI1MCwgNjcwIDMyMCwgNjMwIDQwMCBMMTYwIDQwMCBaIiBmaWxsPSIjZmJiYzA0IiBvcGFjaXR5PSIwLjk1IiBmaWx0ZXI9InVybCgjc2hhZG93KSIvPg0KICAgIDwhLS0gUmVkIENsb3VkIEFjY2VudCAtLT4NCiAgICA8cGF0aCBkPSJNMTAwIDQyMCBDMTAwIDM0MCwgMTcwIDMwMCwgMjMwIDM0MCBDMjgwIDI4MCwgMzYwIDI5MCwgMzgwIDM1MCBMMTAwIDQyMCBaIiBmaWxsPSIjZWE0MzM1IiBvcGFjaXR5PSIwLjkiLz4NCiAgICA8IS0tIEdyZWVuIEZyb250IGFjY2VudCAtLT4NCiAgICA8cGF0aCBkPSJNMjYwIDQzMCBDMjYwIDM4MCwgMzEwIDM2MCwgMzQwIDM4MCBDMzgwIDM1MCwgNDMwIDM2MCwgNDQwIDQxMCBMMjYwIDQzMCBaIiBmaWxsPSIjMzRhODUzIiBvcGFjaXR5PSIwLjkiLz4NCg0KICAgIDwhLS0gQm90dG9tIExlZnQgTm9kZSBOZXR3b3JrIFdpcmVmcmFtZSAtLT4NCiAgICA8ZyBzdHJva2U9IiM0Mjg1ZjQiIHN0cm9rZS13aWR0aD0iMi41IiBvcGFjaXR5PSIwLjY1IiBmaWxsPSJub25lIj4NCiAgICAgIDxsaW5lIHgxPSI4MCIgeTE9IjIyMCIgeDI9IjIyMCIgeTI9IjE3MCIgLz4NCiAgICAgIDxsaW5lIHgxPSIyMjAiIHkxPSIxNzAiIHgyPSIyOTAiIHkyPSIyODAiIC8+DQogICAgICA8bGluZSB4MT0iMjkwIiB5MT0iMjgwIiB4Mj0iMTUwIiB5Mj0iMzAwIiAvPg0KICAgICAgPGxpbmUgeDE9IjE1MCIgeTE9IjMwMCIgeDI9IjgwIiB5Mj0iMjIwIiAvPg0KICAgICAgPGxpbmUgeDE9IjIyMCIgeTE9IjE3MCIgeDI9IjE1MCIgeTI9IjMwMCIgLz4NCiAgICA8L2c+DQogICAgPGNpcmNsZSBjeD0iODAiIGN5PSIyMjAiIHI9IjExIiBmaWxsPSIjNDI4NWY0Ii8+DQogICAgPGNpcmNsZSBjeD0iMjIwIiBjeT0iMTcwIiByPSIxMyIgZmlsbD0iI2VhNDMzNSIvPg0KICAgIDxjaXJjbGUgY3g9IjI5MCIgY3k9IjI4MCIgcj0iMTEiIGZpbGw9IiMzNGE4NTMiLz4NCiAgICA8Y2lyY2xlIGN4PSIxNTAiIGN5PSIzMDAiIHI9IjE0IiBmaWxsPSIjZmJiYzA0Ii8+DQogIDwvZz4NCg0KICA8IS0tIFJpZ2h0IENlbnRlciAzRCBXaXJlZnJhbWUgV2F0ZXJtYXJrIENoYXB0ZXIgTnVtYmVyIC0tPg0KICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMzgwLCAzNDApIiBvcGFjaXR5PSIwLjI4Ij4NCiAgICA8dGV4dCB4PSIwIiB5PSIyNDAiIGZvbnQtZmFtaWx5PSInR29vZ2xlIFNhbnMnLCAnUHJldGVuZGFyZCcsIHNhbnMtc2VyaWYiIGZvbnQtc2l6ZT0iMzQwIiBmb250LXdlaWdodD0iMzAwIiBmaWxsPSJub25lIiBzdHJva2U9IiM0Mjg1ZjQiIHN0cm9rZS13aWR0aD0iNSIgc3Ryb2tlLWRhc2hhcnJheT0iMTAgNiI+MDA8L3RleHQ+DQogICAgPCEtLSBXaXJlZnJhbWUgTm9kZXMgJiBNZXNoIExpbmVzIC0tPg0KICAgIDxnIHN0cm9rZT0iIzQyODVmNCIgc3Ryb2tlLXdpZHRoPSIyIiBmaWxsPSJub25lIj4NCiAgICAgIDxwb2x5Z29uIHBvaW50cz0iNTAsMzAgMjAwLC0zMCAyOTAsMTIwIDE0MCwxODAiIC8+DQogICAgICA8bGluZSB4MT0iNTAiIHkxPSIzMCIgeDI9IjI5MCIgeTI9IjEyMCIvPg0KICAgICAgPGxpbmUgeDE9IjIwMCIgeTE9Ii0zMCIgeDI9IjE0MCIgeTI9IjE4MCIvPg0KICAgICAgPGNpcmNsZSBjeD0iNTAiIGN5PSIzMCIgcj0iNyIgZmlsbD0iIzQyODVmNCIvPg0KICAgICAgPGNpcmNsZSBjeD0iMjAwIiBjeT0iLTMwIiByPSI3IiBmaWxsPSIjNDI4NWY0Ii8+DQogICAgICA8Y2lyY2xlIGN4PSIyOTAiIGN5PSIxMjAiIHI9IjciIGZpbGw9IiM0Mjg1ZjQiLz4NCiAgICAgIDxjaXJjbGUgY3g9IjE0MCIgY3k9IjE4MCIgcj0iNyIgZmlsbD0iIzQyODVmNCIvPg0KICAgIDwvZz4NCiAgPC9nPg0KPC9zdmc+") !important;
    background-size: cover !important;
    background-position: center !important;
    background-repeat: no-repeat !important;
    color: #202124;
    padding: 80px 80px;
    text-align: center !important;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center !important;
    position: relative;
  }
  section.lead header { display: none; }
  section.lead footer { display: none; }

  /* 상단 좌측 로고 조립 (Top 45px, Left 50px) */
  .cover-header-logo {
    position: absolute;
    top: 45px;
    left: 50px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .cover-header-text {
    font-size: 26px;
    font-weight: 600;
    color: #202124;
    letter-spacing: -0.02em;
  }

  /* 중앙 타이틀 (H1) 및 서브타이틀 (H3) */
  section.lead h1 {
    color: #202124;
    font-size: 52px;
    font-weight: 700;
    line-height: 1.35;
    margin-top: 20px;
    margin-bottom: 14px;
    letter-spacing: -0.03em;
    text-align: center !important;
  }
  section.lead h3 {
    color: #3c4043;
    font-size: 28px;
    font-weight: 500;
    margin-bottom: 24px;
    letter-spacing: -0.02em;
    text-align: center !important;
  }

  .cover-guide-box {
    background: rgba(255, 255, 255, 0.92);
    border: 1px solid #dadce0;
    border-radius: 12px;
    padding: 14px 28px;
    color: #202124 !important;
    font-size: 19px;
    font-weight: 600;
    margin-top: 10px;
    box-shadow: 0 4px 18px rgba(32, 33, 36, 0.08);
    text-align: center !important;
    backdrop-filter: blur(4px);
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

<!-- Page 4 -->

## 에티켓 (Etiquette - Part 2)

<div class="card-grid-3">
  <div class="card" style="text-align: center;">
    <div style="font-size: 40px; margin-bottom: 10px;">🎙️</div>
    <div class="card-title">마이크 음소거</div>
    <div class="card-desc">발표자 이외의 불필요한 배경 소음 방지를 위해 마이크를 음소거합니다.</div>
  </div>
  <div class="card" style="text-align: center;">
    <div style="font-size: 40px; margin-bottom: 10px;">🚫</div>
    <div class="card-title">녹화 금지</div>
    <div class="card-desc">본 과정의 모든 실습 및 영상 자료의 무단 배포를 금지합니다.</div>
  </div>
  <div class="card" style="text-align: center;">
    <div style="font-size: 40px; margin-bottom: 10px;">💬</div>
    <div class="card-title">질문하기</div>
    <div class="card-desc">실습 중 발생하는 오류나 막히는 부분은 즉시 강사에게 요청하세요.</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"온라인/원격 환경에서는 소음 방지를 위해 마이크를 음소거 상태로 유지해 주시기 바라며, 실습 중 막히거나 에러가 발생하면 주저하지 마시고 바로 저에게 질문해 주세요."
-->
