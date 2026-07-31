---
marp: true
theme: uncover
paginate: true
header: ''
footer: ''
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

  /* 최초 다크 네이비 / 파란 그라데이션 프리미엄 표지 슬라이드 */
  section.lead {
    background: linear-gradient(135deg, #0d1b2a 0%, #1b263b 50%, #1a73e8 100%) !important;
    color: #ffffff !important;
    padding: 80px 80px;
    text-align: center !important;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center !important;
    position: relative;
  }

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
    font-weight: 700;
    color: #ffffff;
    letter-spacing: -0.02em;
  }

  /* 중앙 타이틀 (H1) 및 서브타이틀 (H3) */
  section.lead h1 {
    color: #ffffff !important;
    font-size: 52px;
    font-weight: 800;
    line-height: 1.35;
    margin-top: 20px;
    margin-bottom: 14px;
    letter-spacing: -0.03em;
    text-align: center !important;
    text-shadow: 0 4px 16px rgba(0, 0, 0, 0.4);
  }
  section.lead h3 {
    color: #d2e3fc !important;
    font-size: 28px;
    font-weight: 500;
    margin-bottom: 24px;
    letter-spacing: -0.02em;
    text-align: center !important;
  }

  .cover-guide-box {
    background: rgba(255, 255, 255, 0.12);
    border: 1px solid rgba(255, 255, 255, 0.25);
    border-radius: 12px;
    padding: 14px 28px;
    color: #ffffff !important;
    font-size: 19px;
    font-weight: 600;
    margin-top: 10px;
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.25);
    text-align: center !important;
    backdrop-filter: blur(8px);
  }

  /* 우측 하단 메타데이터 (Bottom 30px, Right 50px) */
  .cover-footer-info {
    position: absolute;
    bottom: 30px;
    right: 50px;
    font-size: 14px;
    color: #9aa0a6;
    font-weight: 500;
  }

  /* 일반 슬라이드 제목 (H1 & H2) - 파란색 밑줄(h2::after) 완전 제거! */
  h1, h2 {
    color: #1a73e8;
    font-size: 38px;
    font-weight: 800;
    margin-top: 0;
    margin-bottom: 24px;
    letter-spacing: -0.03em;
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

  /* 카드 컴포넌트 */
  .card-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-top: 10px;
  }
  .card-grid-4 {
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

  /* 서비스 및 도구 전용 히어로 레이아웃 */
  .tool-hero-layout {
    display: grid;
    grid-template-columns: 1.2fr 0.8fr;
    gap: 24px;
    align-items: center;
    margin-top: 15px;
  }
  .tool-icon-box {
    background: #ffffff;
    border-radius: 18px;
    padding: 32px;
    box-shadow: 0 6px 24px rgba(60, 64, 67, 0.08);
    border: 1px solid #e8eaed;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
  }
  .tool-icon-box img {
    width: 100px;
    height: 100px;
    margin-bottom: 16px;
    box-shadow: none !important;
    border-radius: 0 !important;
  }
  .tool-icon-name {
    font-size: 24px;
    font-weight: 800;
    color: #1a73e8;
  }

  /* 보안/비용 경고 박스 */
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
---

<!-- Page 1 -->
<!-- _class: lead -->

<div class="cover-header-logo">
  <img src="https://www.gstatic.com/images/branding/product/2x/google_cloud_64dp.png" width="48" style="box-shadow:none; border-radius:0; border:none;">
  <span class="cover-header-text">Google Cloud</span>
</div>

# Interacting with<br>Google Cloud

### 2026 Modernized Edition | Module 01: Interacting with Google Cloud

<div class="cover-guide-box">
  Google Cloud 콘솔, Cloud Shell, SDK, REST API 및 모바일 앱 다각도 관리 가이드
</div>

<div class="cover-footer-info">
  Google Cloud 교육 자료 | 베스핀글로벌 2026 개정판
</div>

<!--
comment:
💬 [강사 대본]
"수강생 여러분, 반갑습니다! 모듈 01에서는 Google Cloud 리소스와 상호작용하고 인프라를 직접 제어하기 위해 사용하는 도구와 관리 인터페이스에 대해 다룹니다. 클라우드 관리자는 웹 콘솔, CLI 터미널, REST API, 모바일 앱까지 상황에 맞는 최적의 인터페이스를 선택해야 합니다. 이번 시간에 각 도구의 핵심 특징을 명확히 익혀보겠습니다."
-->

---

<!-- Page 2 -->

## Google Cloud와 상호작용하는 4가지 방법

<div class="card-grid-4">
  <div class="card">
    <div style="font-size: 32px; margin-bottom: 8px;">🖥️</div>
    <div class="card-title">1. Google Cloud Console</div>
    <div class="card-desc">웹 브라우저 기반 GUI 관리 인터페이스 (`console.cloud.google.com`)</div>
  </div>
  <div class="card">
    <div style="font-size: 32px; margin-bottom: 8px;">💻</div>
    <div class="card-title">2. Cloud Shell & Cloud SDK</div>
    <div class="card-desc">gcloud, gsutil, bq 커맨드라인 CLI 및 5GB 영구 무료 터미널</div>
  </div>
  <div class="card">
    <div style="font-size: 32px; margin-bottom: 8px;">⚡</div>
    <div class="card-title">3. REST-based APIs</div>
    <div class="card-desc">RESTful API (GET, POST, PUT, DELETE) 및 언어별 Client Libraries</div>
  </div>
  <div class="card">
    <div style="font-size: 32px; margin-bottom: 8px;">📱</div>
    <div class="card-title">4. Cloud Mobile App</div>
    <div class="card-desc">Android / iOS 전용 앱을 통한 모니터링, SSH 접속 및 긴급 제어</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"Google Cloud 인프라를 관리하는 대표적인 4가지 경로입니다. 가장 직관적인 웹 GUI인 Cloud Console, 명령어로 작업하는 Cloud Shell과 SDK, 애플리케이션 코드로 연동하는 REST API, 그리고 이동 중 모니터링을 위한 Cloud Mobile App이 제공됩니다."
-->

---

<!-- Page 3 -->

## Console, Cloud SDK, Cloud Shell 비교

| 구분 | Google Cloud Console | Cloud SDK (gcloud CLI) | Cloud Shell |
| :--- | :--- | :--- | :--- |
| **인터페이스** | 웹 브라우저 기반 GUI | 로컬 PC 터미널 CLI | 브라우저 내 통합 CLI 터미널 |
| **설치 필요 여부** | 미설치 (웹 접속) | 로컬 PC 설치 필요 | 미설치 (Google 인프라 제공) |
| **특징 및 스토리치** | 리소스 그래픽 조회/설정 | 파이썬/셸 자동화 스크립팅 | **5GB 영구 $HOME 무료 디렉토리** 및 gcloud 사전 탑재 |

<!--
comment:
💬 [강사 대본]
"웹 GUI 콘솔은 초보자가 인프라를 한눈에 파악하기에 매우 좋습니다. 반면 대규모 배포나 자동화는 CLI 환경인 Cloud SDK를 사용합니다. 특히 Cloud Shell은 로컬 설치 없이 구글이 브라우저 안에서 5GB 영구 스토리지가 포함된 Linux VM 터미널을 무료로 제공하므로 매우 유용하게 쓰입니다."
-->

---

<!-- Page 4 -->

## 콘솔 탐색 메뉴 (Navigation Menu)

<div class="tool-hero-layout">
  <div>
    <ul>
      <li><strong>상단 좌측 햄버거 버튼 (☰)</strong>: GCP 전체 서비스 카테고리 탐색</li>
      <li><strong>주요 서비스 카테고리</strong>:
        <ul>
          <li>Compute Engine, GKE, Cloud Run 등 컴퓨팅 제품군</li>
          <li>VPC network, Cloud DNS, Cloud Armor 네트워킹 제품군</li>
          <li>IAM & Admin 보안 및 권한 설정</li>
        </ul>
      </li>
      <li><strong>고정(Pin) 기능</strong>: 자주 쓰는 메뉴를 상단에 고정하여 빠른 직관적 이동</li>
    </ul>
  </div>
  <div class="tool-icon-box">
    <img src="data:image/png;base64,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" alt="Navigation Menu Home">
    <div class="tool-icon-name">Console Navigation</div>
    <div style="font-size: 14px; color: #5f6368; margin-top: 6px;">Google Cloud Console (GUI)</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"GCP 콘솔 좌측 상단의 햄버거 메뉴를 클릭하시면 구글 클라우드의 수십 가지 대표 서비스들이 카테고리별로 나열되어 있습니다. 핀(Pin) 기능을 활용해 자주 쓰는 Compute Engine이나 VPC 메뉴를 상단에 고정해 두고 편하게 접근하실 수 있습니다."
-->

---

<!-- Page 5 -->

## 콘솔 활용 실습 가이드 01: VM 페이지 이동

![bg right:45% fit](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAmQAAAIhCAYAAADghKZjAAAQAElEQVR4AeydB2BTVRuG33S3jBYoe8gegiwBWQICoogg/CAgioiDKQICyp6yZMsUUFBxIShDEJEtU7YM2XvTQqGs7v++p9yQpEmatmmbtp/y5dx79nluevPmO+eeuHl6esaICQN5D8h7QN4D8h6Q94C8B+Q9kHrvATfIf0JACAgBISAEkp2ANCAEhIA9Am6vvvoqxISBvAfkPSDvAXkPyHtA3gPyHki994DbgkVLISYM5D2Q9PeAMEy/DBdq98lvvl+Kb75fggXf/YxpM+aic7ceyJw1OzL759AsEFm0MGuAFmrGUFm2nFChFufPY9rjY56L5YQwEAbyHoh9D8iUpT3/oaQJASEgBDQCMZpFay/RMQbA4KGJrByoXrMeZs6ehylTpqHDO28jJiYG0ZppB+B/Wnbox+pcS9NKw2AwaNEqldFiQkAICAFFIAGCTOWXFyEgBISAEHhMIFrTVR5evqhStRZmzJyDXr16IyY62lyYaUJMZTcRYgZDrCijiFNp8iIEhECGJyCCLMO/BQSAEBACziAQY3BHsRJlMH3WHLRr9wYotqKo2LTKNd2mvGUMGa9FKU8ZQ/2cx2KPCUggBDIgARFkGfCiy5CFgBBIRgLalGbNWi9g9LhxMMREgyJMU2cq5JQlW9ZFmMEQG6OfM01MCAiBjElABFnGvO4y6tQlIK2ncwIUYVmz5sAXM2ejapUqsaPVpy5jzzSNxlwwesog/wkBIZChCYggy9CXXwYvBIRAchIwuHmiQ8f30aBBAyXAYiXYkxZ1z5jBELum7EmKHAkBIZDRCCSPIMtoFGW8QkAICAEbBGLghhYtW6Nx41cQExWlpi5Ns4ooM6Uhx0Ig4xIQQZZxr72MXAgIgRQiEB1jQJOmryFbzoI4dvIqjp68hv9OXVPh0VPXceTEVc2u4cjJ6zh8nMdp1zi246ev48yFIFy6FoLg2/fx6FFEspGWiu0TCAuPxN17j3Ar5AFuBN/D9SAxV2Uggsz+e1lShYAQEAJOIUBP2YjhA1G+bCGUKZ4bpYvlRpkSefC0dvw0wxK5Ua5kHpRVllcL06ZxbMWeCkTeXFmR2c8LYRGRSpidPHsTN4JCQYHgFKBSiU0C9LreexAOCrD7D8KAmGh4exmQJZM7/LN4iLkoAxFkNt/SkiAEXIGA9CE9EeCasqHDR4IfmGpcMTFPjlUE1CJ/YzrS3n8GgwEeHu7w9fFCQFY/5Mvlj+KFc6JgvgC1P9vZC8FKoD0KE69Zclzdh5o38uat+4iIjNAEsTv8fN3h5eUGd3eDem9B/nNZAiLIXPbSSMeEgBBIjwSyZs1u3KfMbJG/JmTSshCL71r5eHsiT86sKFUsF3y8PHD2YjDoMYuvnKQ7ToBTk/cfhiOTJsJ8vd3h5mZwvLDkTHUCbqndA2lfCAgBIZDRCNSsVSfWM6Z5yDj2GPWiXnmkPBnpVZwZDAYEZs+MEprXLCIySq01kzVm6rIn6eVO6CNERUUrrxi9YUmqTAqnCgERZKmCXRoVAkIgIxOIMXigT5++CoESXpowU6EWo4faYbr+x2nN/HkCkM3fD2c0b9nd0IfJPd50Wz89Y9HR0do0sXykp+WLLFcvLV896bsQEAJplkDRYiU0L1l0bP81r5HmFos9fvxqMGSMvckoyJ7Knw1Xrt9FyN0Hj0cvgaMEuGYsPCJKxJijwFw4nwgyF7440jUhkCACkjlNEYgxuOOddzqqfcliNO+Gps60fzGx55rHLE0NJomdzeTnjacKZMO1G6EQT5njMOlNDb0fBl9v+Sh3nJrr5pSr6LrXRnomBIRAOidQsfKz0FTYk1FqXjGzZdjaOT90n2RIv0e+Pl7qScxL1+7IvmUOXub7DyPg6WmArBlDuvgvLQmydAFcBiEEhIAQ0Al4efnCx89Xnaol/SaeMQoxM3GmcqXvF3rKuH/ZlRt30vdAnTS6Bw/D4e0pH+NOwpnq1ciVTPVLIB0QAkIgoxKI1lRYq5atYr1kj8UYhVhG5cFxc02Zt5dHKm+JwZ64tnGDXQ93g2xtgfTznwiy9HMtZSRCQAikQQJPP10OMdB8Ydr0JHQzHQfjTM8zwHHuwCwIDrkP2TzW9sXWBZntHJKS1ggkiyA7fuI0Vqxam2AWLEdLcEEpIASEQIIISGbXIZAla1ZNkMU+bUnvmCbN4nSO8XEi03EEt8TImT0zgm7fT8ejTNrQIiOjZe1Y0hC6XGmnCzIKqglTZ2P7zj0JEmV6uQXf/Qweuxwpkw7t2f0PViz/DXNmzVAhz02S09zhlcuXoVtyd57tkJfOjhwZZ61dxtOspaV2HPulW2r3RdpP2wTc3T2gRFh0tAqN4kvzjPFYpaXtISaq9zmyZcK9e2Hy25c26EVGRWvTlTYSUzw6Eo/uBCNYu14p3nRaaTDqAUKCQ/AoynaHnS7IgoJvqdYYOirKKMAo4liQ5RgmzZKnNEVEpWdK44N338awwQPw5ewZKuR5k5cbKIGWPC0nb60URew/jSIjOVpjvTonhjo7cvzgPY3nkAFKFOptMz/7Q2P/9HhXCYdp/WXfGLpKn6QfaZWAQf3GI3tPAaaH+jHPM6IZDAYE+Pvizl3ZMNba9eeSQ4PBVeR6JG5dvIjT1x3ZRy4M94KDEfIw0tqwHIhLanmLJu5cwP6Dhx2y8/E8axITFYEIzXNp0ULsafgdXDhzBbfCY0+tvTpdkNWqURUd27dRbVFcxSfKTMUYC/Xr1RWlShbjocsYxYEuIkw7lS9/fuMp81Bk8EOax8YEOVBClVzoGbOGg7xWLPsNFGYUvdbySJwQSK8E+MHKscXwRTftg9ZVPmr1LsUXBgWF4OTpi+rne+LL62h6QFZNkIU+cjR76uRLx60+unIU/+w+YN0OX0XirswDXD9zERduJ1aQJbW8xQWLjkSEJpIy586LQgVsWVZ4h0fCltbSaww5dwT7j11PJBfA6YKMHXNUlKUVMWYqJijCOnf9EPO+/har1qxXxmPGcewUF1euXOahmEaAHiQKVe1Q/SMn8tp/6BhoZMg4JpLd3j3/mHnKGC8mBNIzAQoxM1GmiTFb4w2+fRc3g26DP5NjK09S4xPaRmRUFA4ePoWNW/fj8tUgROuDSWpHtPI+3p4gDvmtSw1GKvzzyV0ClSqWjWNP5/FKfG9iohGtlX706JH2moh/SS1vtUk3ZPLPgRw5bFkWeFst59zIZBFk7GJ8oiwtiDGOg4KCIa1K1WpKgHXp9iF4zDgKNB4zjsKCYoPnTMvoRo/YCs3zRQ5kQvFFTjxmHI38GMc0xpMf45gm5hIEpBMpQcDwpBF7U5Vnzl3BkWPnEMX9Mp4UcepRQtq4G3ofG7fsw2mtX96aeHJqRx5X5ufnhfsPNRfG43MJUpCAuyc8PeOah3vi+xBz6zZus3jILdy2s56KWaxZTMgd3GVCSAju8tsMj9OJJZsgIx9boiytiDEKChrHoosFHtsyCgvms5XOeHqBOC1Ho9jj+ii9DabbMr0cp071crby6vGmZdie3g5DR9tlXczL8glpm+XYT4a0EaPGwp7QYhrFGPM6YvrY2AaN/WM/LcsyH+Nplmn6OdNozKvH6SHrpbEN5iE7PU1CIeB0App3KTwiAuFhEeZV001kHmP1LFoTamFh4QizLG+Rm+lhWj7mt0hK0GlEZBR8fLzwUv1qyJsnMEFlHc3s5+OJh/GMx9G6JF8qE4i6jTMX7sE9ZyByGu7izLnbSJAmi7mPixc1OZY9ANkQgnNXHFmzBgf+i8Z9PpQQHIxgqxaKsHhriVBTn/Fms5MhWQUZ27UmyvQF/ExP9TVj7IQNW7niN2MKBYXxJJEH/FDn9Cen8Gj0HqlF7e++DcZbq5YigQ8SMJ1lKAj0coyjWLBWjuKJ6XoZhoxjfh6zXdPxWauDbbEO5mUZnpu2ba2MHse87DvPR3xmX4wxj6PGOjkG9ot9Yn9oPGY/mWZaF0UU42mm8fox+8k0mulUM9vR22DdbIN5eA0t29DrklAIJJbAnn3HcPVaMNas34U/1u7EqrXbsWHLXjx4GDutczskFL/+vgXnzl/VpixDsEw7XrV2Bx49ivUcUVgdOnoGv67cjBV/bNNsq7KLl26YdelmUAhWrtHTt2l1bsbxkxfA8rfv3NPObbdhVtHjkxzZsuL5GhWQyc/ncYzzA24SGx6e2PVGzu9PhqrxwQ2cPXs2jl28bfGFwREoYUE4eeg8gr1yo+xTBVCosD/cbp/H4fMhiHDE0xV9H5eOnsS1qKwoWrgwihbJiogrp3Hs2n04UtxmF9084OkF3Lt+FRcu2bK7CPPygIebzVq0hHCoP0dtKjb2r/YRrhw2WX93+Hq8a8vsVq+14JR/lqJMr9SVxRj7yA9rhjR6cBgm1vhBzg91lmddnN5s1ryFcepTFwBM180yzrQc8zCdospSIFB46X3Xy+ieO4oLPY112DLmYT1sQ68jvv6a1mUqbqpUqWaalKRjcuQYWIm1fjGNQorpSTHWwbGzDtN2GEfm5MM0MSHgDAKc+vvv5HlUrlAKL79YHVWfLYP7Dx5h/78nwTVamfx88dyzTyMwhz+yZMmEalWexrNaXg9Pd9U813AdP3UBFcuXwKsv1cTLDZ9Djuz++Gfff7hyLUjlYX279h5Fdk1EMZ35ypUpikP/ncG168HI5Otjtw1VSSq8eGrzYxERCfKjpEIvHWsyzeUKu6d9AbiL+xb4PfyyImeAL9wdGVDUA9y+dAL7D11CiFcgni6dFz4GwD1bEZQvEQDcPIf9B0/gyp0wG8IqGhF3ruKY9rdwJTwzijxdFNncWb4oyhbyxv2LJ3Hg+FXcDefKNEc6ZJHHvxAqVSjnkD3lb1HW9PTBbdwOZ8Rd3FZPY/ogX7mKqFb1sZXLDR8m27EUEWRsPzBHdgZG4/nxk6eN5654wA9f9otChKGl0ftC0WLLmM4yDHUxRmHE9VKc3qTXjdN0FGfMx/ZYF49pfOqQIY35TMvxmEKBZUwFAgWLLhZYL/OxLb08y7C++IzChnni66/eFvOa2t49/xhPHW3TWMDGATnq7fGa6GMjRxrHy6JkYilSGe+omV4DnRsZsg226Wg9kk8IOEogKioaz5QtilyBAfDx8kTBfLlQslhBhNy9jzDta7eXlwfy5cmBzJn9wIXu+bTpwTy5s8PD3V27+d/DuYtXlRgrXiQ/fH29kUXLV00TcDmyZ8WJUxfBqcXwiEjQChfMo9KZr2SxAmj2ci3kyxsItpFfC621wYX+ly7fgKmF3nPWdJF9Su7ubsm6Zs5+65IKeCJ7/iIoUsTCCgRoKfb5PLhyFLv3ncDJ6+HIlK8oKpYpgMyamNJLufsXRoUKRVHALxyXT/yH3Xv/wzWTXU7Cgs/i373/Yv+JGwjzy4NyFYojp7deGvDJXRKVy+ZBprAbOHbwEPYePYvgR0/S7R5pQjHE6vSkrWlLPT4E1vYSu3sjGGGZc6KAfwxuXg9KHmLoMAAAEABJREFU2FTs4466PQ6TNbBcM8bGgoJvJXjzWJZLDeMHvLV2GU+BYMt0UaKHrIMf8AxNjR/2FBiMM/UssX7GccqPwojHulHkzPvqW3Wq5+MJ+8KQ+Vkvj3UzLaPHWQtNhY8ucvR8FDoUgPq5Ltz0c8uQbVrGJfZcb4tjozgyrYftcLxMY7xpH3meENMZ8pro9enl2Y5l23qahEIgsQR8fSiiMpkVz5o1EyIooiIt3BNmuTQHw83biInRIqNjzATTdc3r5e3tpTxtUVodfj5eygu2e/8xnDpzScW7ublpQsxTK2z/H6c+Dx45DVO7HqSWZtsv6IRUg8GgjY8DdEJlUkWKEvDLXRilypRB1crlUDJfVnga2Pwj3Dh+GMeuP1ZOnlmRr2Q5LU8ZPF38KeT0ZZ5Y884SgIDcBfB0hWdQoWQe+FlRLAa/PChZ/hlUKpMfubX8WeNzQ8VWDUTcwzVbU5TnLuL02Us2pjBv4K7ljO39Szh7E8iRJzfy5Q+E953LOHMr4dPsVoan99Y5oaUY4zRlQvYpc04vElcLP3xZ0lQk8Vw3pvND29L0dD00/YDX4yzDps1aqCiKK+anKFIR2ksVG1N+bF8XDLpYYXmtCJ61U4bpjhrrZ50UYlzLxnZ4zrYp1myJk7x586smmJemTpL4otfT9LVYVtaq08et57WWx14c2evpel36uR6SCcevn0soBJxFQH1eaZXZe9JSSzb7Fx0dDQqu/05cMBNMFE+3bt+Fn+Yx0zQNKM7q1KyAAvly4sChU1i9dodaZ3bq7GW1hsysUouTis8UR5NGNcyseOHYv3GLrE4/JQuDweD0eqVCZxDge8/OVKG7H7Jm9obl5YvkFw3L7xnu3sjs72c+DeqVDYUKBCKzV3xSxQ2emQNRoGA2xP/1ArH/+eRCaRtTlaVyeQBaehmr6SWRy1T0RQTj9IkgzTuWF4WyeQB+BVAij+a5PnMM5+8kTJS5xfYseV6tiTFu+mq5piy+zWOTp3fx15ovX+wNhx/u/KC2LNFMEwYUJJam5zMVJYyz9QHPNL0tHtPYJkOaIx/+FI2OlomvPt2jx3ycAuV6KgoxvS8UYpy6o0eKeRhvaRQtehz7ph8nNrTG31pdpu06Wsa0HtO+2hLCzG95vRgnJgRSgwC9XD6a6Kr/fCUzwaQLqBeerwyKMfaN05RVKpXG/5rWxUsNqmlTlTnV+h16zJjuisbpXHc3gyt2LYP0KQK3Lscu7D/531Ht/XJY2d69B/DP7n+xNwkboboEQPXgwmWEmHi9wsIdE1IRd6/i2OGLCEZWlCiZyygG/QqUQolsMbh+4gj+vRhqY21c3NEnmyCzJcb0LqQFUUbhoffX0Q93M89W1WqquC4SVi7/TZ1be9ljuuZKE4J6GeY1FVo8NzVdQJjmZ7rdMpcvM4tNMxWSK5bF9pleQIowGoWYzcKPE0wFC0Xd4+hEB6b12R2byaa8pmVsNazz09NNy1im6XkY2ktjupgQSCkC2bNnVVObV2/G/mydabtc83Xn7n0VxScyKbzCwiLgpgmcrFkyoUK54sgZGACuEaOnTWV0sReuf/P0dHexXiV7d1yjAe/M2vsjKzI9xu/ln0vzWGmeoAJ5UaxUaVSqWA5Vy+WNd7F6qg0mJhraP/vNqwcX7uCBYxrMrC63qIcI8w7E0+VjHzQwJho8ka2YNgWbPxvyBGaBwZgQ9yAm6omHMVkEWXxiTO+Sq4uyfJow0j1A9BBx2k7vu7WQQoH59DRdJOmeMXsf4rpXimXZJtvmMc1WObZHYx62wXJ6m6b1MV03U8Gox1mGeh2M5zF31KcXkPUzjqa3y2Nrxrxc+8Y05o2PHfNRuNkSvqyPxny2xsY0U9Gr52c8zVrdpvmZx5S7rXVoHA+N+cWEQEoS8PXxwq2QUISE3EVYWDgitZt59oAs4EL9A/+eBKcfue6MduzkBeziIunrwaqL9x8+wr9Hz+DA4ZOqLKcC77CuO/fgr4kzN7fYjwNrbagKUumF3govL20qKJXaz9DN+uUyW8z/VL5A5MiRQ1lAZh94enrYFhu3z2getANW7BguPQQeXT5mJY35z0CtTrRZnnns2ePyCMX5A/+qhwpumni/HLme2YpVRDUHhKZ7tqKo8HQBswcVntTvgcz5CiGX75MYy6N75w9p/fsXxx530M0yQ1LPHRVjejuuLMr4ga4vnGd/KbZsCYs9u/9Re4ldeex9Ml28T1HD8kyj6OCxqbGsqSeKaWxbL8cyzMN4U2O8fq5Pr+nrq5jfNJ35VPuDB/DQrlGUsH1mohhkXTzWTdXz+Me1LdP0PAzZJ30MZMenF1mWaabGOKaRAftsq059nR3TrV0HxtNYt+7d1NtnnJ7GYxrbtYzjuPUyTGMe5jU19tH0XI4TQUCKJIpA0afywdfHG5u2HsCqv3aCTzpSSJXXPF3FCufXppJOYNmqv5Ud1sTX06ULo0SxgqqtHNmyomrF0mq/M+5VtmT5JvVzR3xas0SxAioPX6y1wfjUsgePIuDr7ZlazUu7iSWQKSeKFS2YCMuJzGyT21FY+dkmaz/lZB5XCAHgf25w92DomEVGRmie5nhM+wLkWG2O5XLzcDfL6HRBliNHNmMDXMDPNWPGCBsHlqKsVIliNnKmfDQ/oHVPD1unsODi9iYvNwA/mCkkeM6Q6TSKAf1Dnec8ZhyPKTpYloKCxnI0pqm2Ro3loTLdK0VRwLZo9HCxHOugYGBG9o9leWwqgvS2WD/z05hHz8tja8Z0ts0007bZvmnbTGMeW6bXw5B52F9u5cF+6HXpfWMa81AMkhePLY1r9vQ0XgfWofNgv1gXy7A9fVqV9TGORo8Xy7AtlmNfmJdppmY6duZhGebX22B50/xyLASSSqB2jWfg42UuOvLmzoHmr9RGNn/18aSa8PPzAXfFb9a4Fpq8WB0BWTOpeA93N1QqXwLNX62Dpi/XUtZCOy5T8ik1PakyaS8FC+RCs8a1NYvNw/zVq5RVng4tWf2z1YZKtPNStVJp1KtdCdw3zE62BCc9eBCOTL5eCS4nBVKZgFcW6N60hIVZYtdiccNWT094Jtg8HnvtMiF7gBf88hVATvM/LStgwnHt2BHsPxCPnVMbjFkpn7gov4Cs8PbLjcKBsR10S1w1tktxf7FxowbCUTGm16SLsoSW08snZ0ghwLVTuhhgWxQjFDyWH84UR126fcgsZkaBoIsylqWgoOnlKQzYhmkhxukeOpZhe9wtnuV4zrxsj/3jMY1lKCiaNY99EpH52AZDpjO/qUhhnDXjWE37y7ZpbFvPTy8g8+nn1kL2h2MwrYt90eti3/RyrIt16ueWIevi2JiPaaxD56H3i3nYHtNpPOeYeay3S+HGcozT+8Vj3VhGj9fLMD/bYH/JVu+DXkZCIZBSBNzcDGqRPhfqGwzmq1Mohny0aU2auybSrPVJL888zG8vj7U2rOVPrrhHYRHglh4+PrEfWMnVjtSbVAIeyF6wIIrl9ktqRc4rH3kbVx9kQ/G88fRJm3asVrUiHLJi2RLfPy9/FCqaD9mN3y0icPvaA+QsmhfcKBfaf26aOf0fRZkjnjHLhmvVqIrElLOsJznO+SFNsUDTP5AZR+OHMz/AudbKVBxZ9oNpFF0UCCzDsizHOhlvmZ/nzMM0ltHbZVmWYzzrZD5TYxkKF6br5UzzcxqS+fXF+3p9zMN43SgiWQfj9bZ5TONYWU7Pay9kf/S69P6wLOMZsj62Qw6m9TCeli9ffmM0yzCfZT3sH/OyHuYxFtAOyIjxzMP2mM68FG70KPKYZtqO3l/LMsxHtpwa5jFDrQn5JwSEQDIQCLn7EP5ZfJKh5vRUpSuMxQM+/jmQI7M3XOY/j2woVuqJ2EFq/+fuh4AcAfBx1zviiWzFSiKfr34OuD05lCNHCPADnR/IFAX8kKfxmB/g8ZWnEKBRILAMy7Ic67RXVi+jt8uyLMd4a+WUV2f5b2A622I50/xMZzmmM2T7TKfpcYyn8ZzxrENvl+dMS6ixLr0/rIvjZ8j6mGZaH88ZT2P/TNN4bFkP+8e8TLNmrI952B7bZV7G0XhM47FpWZ5blmE+5mH7PGbIczEhIAScS4APHYTc0QRZVpNPLOc2kaZro3OUjNL0IKTzZgREkJnhSPsnXOuk1mgNHgCuebIcEafr9Dh6h/RjCYWAqxKQfmVMAsG37yOz5nHxlicsrb4BuG4w+smOCVbzSGTaIiCCLG1dr3h7S5FFzw4zchE7BRhFGsUZj7kGimmcitPz8VxMCAgBIeAqBCIjo3Dz1j0EZot9aMFV+uVK/fDwcENUVIwrdUn6kkQCIsiSCDDpxZ1bA0UW10Yx5NQkBZjpgnS2xilATsXxWEwICAEh4GoErgeFIkdAJvh4y2J+W9eGnsNIEWS28KTJeBFkafKy2e80xRhFGRedU3zxnEavGOO4jsp+DZIqBISAEEgdArfvPAA3g80VmCV1OpBGWtUFWXR0ArxkaWRsGbWbIsjS6ZWnAOOic4ovLmKn0SvGuHQ6ZBmWEBACaZzA/QdhuHrjLvLl8k/jI0mZ7vv5eiEsIjplGpNWkp2ACLJkRywNCAEhkEIEpJk0TODho3BcvBKCAnn8IfuOOXYhM/l6IiIiRtaSOYbL5XOJIHP5SyQdFAJCQAikbwL0jJ2/dBt5cmVB1iyyzYWjV9tgMCBLJm88DIt2tIjkc2ECIshc+OLE6ZpECAEhIATSGQGuGTt/+Tby5c6KgKx+6Wx0yT8cXx9PeHm64+EjEWXJTzt5WxBBlrx8pXYhIASEgBCwQoBbW1y+FgIKsqIFc4hnzAojR6OyZvaBm5ubU0WZo21LPucREEHmPJZSkxAQAkJACMRDgLvLB926h5PnboK/pVm0UKCsGYuHmSPJ/Ikpd3c33HsQJWvKHAHmgnlEkLngRZEuCQEhkNwEpP6UJvAoLALXbt7F8dM38Cg8EkU0r5hsbeHcq0BPWSZfL9x/GIWHYVGQLTGcyze5axNBltyEpX4hIASEQAYiQA8YpyP51GTI3Qe4cuMOTmneMD5B6WYwoEihHCiQJ0A2fU2m9wTXlOXMnknzPnoqb9kDTZyFh0crrxmvTTI1K9U6gYAIMidAdMUqpE9CQAikPgF+ADpip88H4cTZGzh25jqOnb6O/05dx9GT15QdOXENT+yqduzaxr5zPFdv3NUEQTi8PT2UACtRJCfoEeOGpql/ZdJ3DwwGAzL7eSFXjszI5OcNGNwQFh6D0PtRuBMaKeaiDESQQf4TAkJACDiPgKkAc7TWYk8FomSRXChdNDdKF8uNMsVz4+kSeZSVLZkHTyyvduzaxn6X0sZQtFCgEmI5smWSNWKOvhGSIR8FMKcyswf4KYGWOzAznGxSn5OYuiXD9ZcqhYAQEAIZioA1EWaMsyBhjI+JgX5skUVOhYAQSMMEYrS+J+ZvWwSZBk7+CQEhIARsErCTYHnTVeeW+TXhFVCeQ+gAABAASURBVB0dDd1UHi3ONIwtom7j0FSamTGfHsdjsSdCVlgIC1d8Dxi0P2iDwQCDwaAdaX/O2iv7qQV2/4kgs4tHEoWAEBAC1gmY3mBNjymeKL4Yx9BomgiLfmyWaSyjJTHAY1lmDNm6HsdjMSEgBFyHgMGgiS5T07rGv29T03I8EWf8Q9fyWPsngswalYwVJ6MVAkIgAQT0Gy2L8JghjcKL5wwpvHhM4znDGM1LFhMVBVo0Q55rptK1CnTRJeFjj4IwMYpyeU+43ntC71FMTLR2qBuvlPbGffzPYNCkmGYxmgjTzWDQ4rR0nmuB2T8RZGY45EQICAEhYJuA6U1Uv/UyTjejEKPQ0kRXlGYUX7SoyEjwPDIqEqYWpZ2zfKx7TKtVu3nHHus3eQlh9qEnPNIuj/Rz7fg3a26aLtP+do1x2m0kRr1vtb9p7VhzkfEVMVoeHhgMBiW4eaybCDKdhIRCQAgIATsE9BupHmp3Vu1fTOzaMO0mqzxdmgCL0owCLIICLDoK4ZERCIsIR1h4GB6FPUJYmBY+eoRHJsY6Y7Sbt5lFxyBGTBjIe8D13wPa33/s3672N6vdQ2Jfod0bgBimaXHQ/r4ZUJipOC0+1lcWm4dpbjv2XYCYMJD3gLwH5D1g+z2wfe/52PukFu7af1E75rlm2vnO/Rewc+85MNyxT4vbfx7b9p7B9j2ncfLMDdy+E4aYGHf4ZcqCgGzZkU2z7NlzwNTmzv8Ws+cuxCzNZs75GrQZc74Cbfrs+ZhB0855LDYfwkAYuNR7YNZ8fDFzHsZOmII+/frj9dbt8MwzFTSlFQ16zSm2NP0V6xHThZkWSWGmBZpG07xlWga3GpULQUwYyHtA3gPyHrD+HqheqaC6R6rw2afwnHZerUIBVKtYULMCqFo+v7Iq5fOhUtncKF8qENUrFUb92mVRsVwRPFUgJwL8M8PL0wMGyH9CQAikRwIGgwGZM2XGqZMnEK55w4sULYqXX3kVBQsWwvVr13Dl8iVlly9dwuXLF2OPr1zWvqzFTmkaDAa4Qf4TAg4TkIxCIGMR0L/BMjQYYr/FcmqSFGKio9XNlNOTkdrU5KOHD7VvwDHaTTkTMmXKBHd3d2YTEwJCIIMRyKQJM3//AOTKnQf1G7yI7j16omLlyvDw8ICnlxc8PWme8Pb0hMEQe18hIhFkpCAmBISAELBDwGCIvWnqYowhBVlUVKRaoP/o4SN4e3nDP2sAvL19IP8JASGQRAJpuLgSXprY8nxsWbP649WmLdDo5VeUAHNzc1Oh9qK+1BkMsfcXtzQ8Zum6EBACQiDZCNArxso5ocBjZVqEUYxpXrHIyEiEhYfDz9cXmTJn1lLlnxAQAkLAOoHKlatowqy5EmEqR0zM40ALNVEmgkzhkBchIASEwBMCFF88U6F202SoCzEeR2liLCoqCmFh4aBnzE+bomT+BJhkFQJCIAMSeLpsOTR48SVEI1aExcSoI2gqTdaQZcD3gwxZCAgBBwkYDLHL8GM0UcYiDDlVyTAiIgLuHm7IkiULk8SEgBAQAg4RePbZqqhQoQLc3WLg5WGAl3sMPD0ggswhepIp4QSkhBBIowQotth1hkbTIijE+C2WC/jDNTEWoU1Vcs2YliT/hIAQEAIJIlC3XkN4eXqqbTE0XxkMWmk3zeSfEBACQkAIWBAwGGIX2ipRxicqtfQobXpBPVUZHgEfH1+4y5OUGhX5JwRSl0BabN3X1w9VqtVETHSMmq7kfmUiyNLilZQ+CwEhkCwEKL5YMUOaOlYvMdqNM1pZZFQUwiPCkSmzTFUSjZgQEAKJI1ChUhXEaP9TjImHLHEMpZQQEALpnYDmHeMQlSiL4S1T+xKrRURFaaJME2SeHh7w8Eipfca0huWfEBAC6Y6Ar68vnilfSU1XRmueMvGQpbtLLAMSAkIgqQT4bZViLEariCE0UcYnKynN+BuVnt7eWor8EwJCQAgkjUCJUmXUOjKDm0EW9UP+S3UC0gEh4EoEKMBo7BOFGcVYdHS05iKLQVRkJCIjI+DjJYKMfMSEgBBIGoFChQqre0uMdo8RD1nSWEppISAE0gkBXYTpw+G5MkZoU5gxWqg5ykBx5iWCTKMh/4RAmiPgch3OmTM31L1Fm7gUQeZyl0c6JASEQKoS0MSX3j4FGT1knKrkcUxMNLiOzF3Wj+mIJBQCQiAJBLipNL/oaW4ymbJMAkcpKgSEQDokwGnKGO0OSTMO7/E547iWzBjvagfSHyEgBNIUAYPBoHnI6CODCLI0deWks0JACKQcAe1GycYowmjKUxYdzSgxISAEhIBzCWhf+lJ9yjIo+JZzByW1pWcCMjYhkLIEtJtknAatxcXJJBFCQAgIAccIGB5nSzVBtm3HbvQfMsZoC777GSLOHl8VCYSAEEg1AsobZtK65blJkhwKASGQbgmk/MBSRZAdP3EapgKMQowCjXEpj0BaFAJCQAjEJaB/a2UKRRmNx2JCQAgIgeQg4DRBtmLVWkyYOtth0wfTrEkj0HhOoWZaB+tkvJgQEAJCwBUIpCdR5go8pQ9CQAg8IeAUQUYhRfHE0BHTm69Vo6oSYzWrV9GjYFqeddJ7ZkxMhQPegE+fvYyxUxbh1bb90aB5b3TqNRFrN+zGo7BwY4/CwiPw9fersXTlZmNcSh1cvhqk+nfs5AWrTTKe/Wc+axniS7dWhnF/7/gXk2ctRmjoA56KCYF0RYB/+3EG9Hihf5z4FI64c/c+NmzZh+s3b6dwy9KcEBACyUJAu7c4RZCVKllMCSuGjlhgjuxqPBRfnKpcufovdc4Xpul10HPGc8anhj18GIbBo79Cs3YDsfyPbShVvCBqVy+PkLv30HvQDLTqMBRnzl1RXYuKisKWbQexd/9xdZ6SLyF37mHJis24dj3YarOMZzrzWcsQX7q1Mow7ceoiVq/daSZMGe8aJr0QAkknEJP0KpxWw8CRc/FOt7F48PARLl25iX7DZuO/4+ds1h967yG27zqsvjzyCySPbd0DbFYiCUJACKQYAacIMvaW4qlfr65wxPr26sIiahE/141RlDGCQmzcqIHGOlgn41PDeNOj6Fqzfhc+H9EF29bMxKTPumNE/45Y/PVwrP11Evz8fDB19hI8evTEU5YafZU2hUBaJ0BPOB/y4ZIFlx2L9g02OfvGL3cUTpb275HTCWr2+o1b6Nn/C9Ro1BWfDp+DlX9uV8bj2o0/xNtdR8OWtzxBDUlmISAEYgk46dVpgiwh/aHXi2KLAkwvx2OKOf08tcOVa7Zj+z9HMG5oZzRpVAPubuao8ucNxIIZ/fH5yC7w8fGy211OZ94MCgG/nVqdBrFbOm5iZGQUgm/dUd+U46amTkxUdDRu3b6rjMep0wtpNa0SoLecoowhhVlaHUdS+r17/zGM/+IHo42b+j36DJmJJcs3O1ztlWtB6PjhONy7/xBrlkzA33/MwPTxPZXxeP2yyciaJRM+6Pk5mNfhiiWjEBACyU7AXGU4uTneYLkOzNQLpjdBQUYBRo/Y/FkTlVdMT0vtkK7+Zau24qX6VVG/TiWb3cmkech8vG2LMa7z6Dd0NirXfR/1mvZErZe7o/Hrn4A3Xr1SCrWGzT/GV9+t0qNUSA8dpyc4TaEitBcKsS8XrkCluu+hTpOPULV+Z/VNOCg4REt13j/2hX1i30xr3bR1P5594QMcOWY+TcLxNGn9KZ5/pYeymo264Y91u+AM8WnavhynXwL8QkbjCHnfyIiirE2L+li/bIrRVv40DhWfKYGnCuYmFofst9//hpv25ZFe/QL5csYpkztXdnw26H1kyeyHhT+siZNuI0KihYAQSAECySbI9G+6FGSckqQos3aTpbcsBcaZoCauXL0JLuSvW6si3N3dE1RWz0xR9/GgGdiy/SDGDeuMTSun4ddvR6HIU3nxrvYN9q+Ne/SsDoVcozZm8iLMmPcrur7bHH/9Ngkrfxyryn4ybA7CwiLUsc2XGCDkTigosiztbhIW5V+9Howho79Cq2Z1sWH5FNWnqpVL45Nhs7Fu016b3ZEEIWBKgPeBju3bIKOLMlMmt2+H4sKl6yhWJJ9ptN3jy1duovzTRZEju7/NfAH+mVGscD51j+M6WZsZJUEICIEUJeA0QcZvtRRhuk2YOts4ENObLIWZnie+0FhBCh9ERkWD026ZM/kkuuWVa7bhwOFTmDetH5q+XBM5AwNQqkQhNXXwYr2q6olMijZHGzj031n8+vsWfNS5lSbIXkO+PIEoqt1Uua6tYb0q8Xqj+EQonw6lp87SBoyc62g3rOYb3r8j3n/7VfDbN/s0dmhnVKtcJsFjtFp5SkRKGy5BQESZ+WU4eeYSorR7UaECTzxk4RERCAq+o75cQfuSZV4CyJzZD2cvXIO9ewvvBUG37iJ/3pzw9fW2rELOhYAQSCUCThNk9H5RhOmmj4fTkjRdlNFbpueJL2Sdej1pKeSaMW4J8XyN8ihburBZ1z083JVA4832/MVrZmn2Tg4eOgX/rJnQuMFzMBiebFnJ+l59qYZZnLV6fLSp1blT+ypPHb11pjZ2aCdrRRyKK5g/F2pWK2uWN0tmX7zRsoH6Bk5vo1minAgBOwR0UcaQ2fhFj/cJHmck4/IErmOtUbWs2ZTlwcOnwWUPnXpNBIWVJZMWrz6Pc5ogm/XVb1bTWWb+t6tw6OgZvN68nmVxORcCQiCZCdir3imCjDdNe40kNo310hJbPrHlAnP4I3tAVvDml5g6oqKiwKkAPx9vq1OeuXJmUx6toASs/eIN2tPDA97ennG6xEW61uLNMmoaLsA/i/LU0Vtnalmz+JllTchJnlzZrX7LDgwMUE+hRmrf8BNSn+QVAhRjpnsTBgdnvL22+IVu8/YDoMAyXTZRtVJp7N7wJRYvGGH1YaIyJZ/CF+M/wtqNu1Hrpe7oM3gmfly6XhmP6R3/6df1mDrmQzyjTW3Ku00ICAHXIeAUQcYbKBfn0xOmmz5ETlHS08XpScbRU6bniS/kYn/WzXIpabk0MVG3dkW1MP3y1aAEN22AQRNibnjwKEybcoiC5X98GtFgMCAwR4Blks1zesKio6NBs8x0N/R+/GvILAs56fxWSKjVtoOCQvDgwSN4uDvlLeak3ko1aYEAvehce6r3lWvL9OOMEPLpxwnTf8SrL9VUU/8JHTNF23OVyyBvnhzKuPEzLXu2rAjImhl1NM/9c1WeTmi1DuaXbEJACCSWgNM+LSmcKLZ002+i9HDR2EGmUYQxdMRYJjXMYDCgbYv66tHxwaPng09LWvaDTxD+sW4X+BSlZTrXZVSuUBI79xzF0ePnzYrS08UnoTjVx6eg6NnKnj0rzpy/qrxmeubLmhA8duqCfooKzxRX/di07YAxjges7/c/d5iVZXxSjGvBbt8JxQ1NVOn1cLxbdx3WT43hmXNX1DiNEdoBp0U4xmJF8iNf3pxajPwTAo4R4Bc3fonTc+v3C/08vYcUiBEYAAAQAElEQVT8e3r3w/HImzsH+n7YFvwiltgxB2b3R7f3mqu9E7l/Yu9ur4Me7cTWJ+WEgBBIXgJOE2SW3axVoyroNeP2FhRfDHlztcynizXL+NQ+L140PyaM7Ir/TpxHy7eHYPGyjWrfHj6heODQSfT4dBr6DpmlPGFenh5xuss1VLlzZkOvgdOxbdchhEdEKoHDnzBat3kvur3bHAH+mdXj5+XLFgM3oOVTiczHHfAHjJiLe/ceGustV7oIXn25Jvik5ZLlm8B1atzXjPUtX73VmM8ZB6VKFISnNqZ536xUfeb06/zvVuEXjYG7m5tZE+6aB2zk599gxR/bVJ+Cb93ByPEL8ffOQ3j3zVe08fma5U/rJ9L/5CNAMWa6Xoz3C947kq9F16mZDxHxoZ0W7QejUIFcmDz6Q/nbcZ3LIz0RAilCwPzT1clN0mumCzGGptVzWqL/kDHQjd+KXU2ccUHt8kWjQcE0QhMZL7boo/YTe7PTZ+Ai+0F92qs9fegRMx0bj7Nr0wNfffGperycC3Ar1XkPLzTtCXqzxg/vjIb1nmU2GAwGfNC+CUoXL6TEG/PxptywXhW83KCaysMXDw939O/ZDq81ro1h4xaovc24r9k2zWs17JN3rK4nYbnEWHHNs9Wzcyts3Lpf9blK/U6g6Bs18D1ksVhvVqFcMfT5sA1GT/pO9Yn7o/25YbfG5T3jGBPTBymTsQhkZDHGKx2hfWE7duICenZphVkTP1YP8DBeTAgIgYxDwEKQpczAefM1FWAUYhRojEuZHjjeCqfvJo/ujn2b52PTymnK+DNKW1ZPR7tWDY1TCn6+Plg4awDGmDyxyIcD5k7th51rZ6tyf2tltq+dhcYNzZ+UZBuL5g5WP8/ENrhot0vHZpg4qptZfRR+Iwe+qxb1Mh/rW7V4vHpaau/GeahXu5LVgTGe6ZZPfOqZLdMNBgPo4ftn/ZfGfi//YQyaNa6lNq3U63lPE5Lfzh4E7kGmmKz6Als027VujsprMBj0JiQUAnYJ8B6gZ+jXq6txPzI9Lr2HfAp64MdvKa8yv3wldLwnTl9Ci7cGoUHz3spW/bUTew8ex6tt+qtzxvOYcUzjOY1lWDah7Ul+ISAEnE/AaYKMi3A53eCo6UOh54zGcwo10/Ksk/GuYN5ensYnFDnVaDA4LjboVeJTjfSaubtZR24wGMB6mY/izt6Ymc589uqzV97RNH3MjrTDDxFuRknjsaNtSD4hQAKcmuS6Uy5z4DHjxBwnwOURPTq1xKcftVM2YURXTBrVHf17vanOGc9jxjGN5zSWYVnHW3JiTqlKCAgBMwLW1YFZlvhPKKQonhg6YnqNXGdGMWb6iLtpedZp+s1ZLyehEBAC6YsAlzfwfsAwfY3MeaN5tlIp1KlVAe5Wfj2EexTWr1MZjepXTZCxDMs6r5dSkxAQAokl4BRBxm+0FFYMHTH9pkvxxanKlav/MvafaXodrJPnxkQ5EAJph4D0VAg4lUDLpnXVlCY913xCm56uMqUKO7UNqUwICIHUI+AUQcbuUzxx7Ycj1rdXFxYBvV9cN0ZRxggKMU5Z6HWwTsaLCQEhIASEwBMC9GrRuyXTjU+YyJEQSOsEEi/IkjByer0otijA9Gp4TCGmn0soBISAEBACQkAICIGMQiBVBBnhUpBRgNEjxh35ecx4MSEgBISAEBACpgTkWAhkBAKpJsh0uPSW6ccSCgEhIASEgBAQAkIgIxJIdUGWEaHLmIWAOQE5EwJCQAgIgYxOQARZRn8HyPiFgBAQAkJACAiBVCeQIoIs1UcpHRACQkAICAEhIASEgAsTEEHmwhdHuiYEhIAQEAIJIiCZhUCaJSCCLM1eOum4EBACQkAICAEhkF4IiCBLL1dSxpExCMgohYAQEAJCIF0SEEGWLi+rDEoICAEhIASEgBBISwRcTZClJXbSVyEgBISAEBACQkAIOIWACDKnYJRKhIAQEAJCIG0RkN4KAdciIILMta6H9EYICAEhIASEgBDIgAREkGXAiy5DzhgEZJRCQAgIASGQdgiIIEs710p6KgSEgBAQAkJACKRTAmlYkKXTKyLDEgJCQAgIASEgBDIcARFkGe6Sy4CFgBAQAkIgQQQksxBIAQIiyFIAsjQhBISAEBACQkAICAF7BESQ2aMjaUIgYxCQUQoBISAEhEAqExBBlsoXQJoXAkJACAgBISAEhEDGEGRynYWAEBACQkAICAEh4MIERJC58MWRrgkBISAEhEDaIiC9FQKJJSCCLLHkpJwQEAJCIA0SuH7zNjZs2Yc7d+87rffx1RkWHoGvv1+Nv3f8a7VN9mXL9oNO61NUVBR27zuGf4+cttqeRAoBVyQggswVr4r0SQi4LAHpWHISOHPuihItj8LCbTbDNAob5rWWieLn0NEz2LR1P24EhSAmJsYs23/Hz6HfsNm4dOWmWbytk8jIKFXXJ8PmoHXHYfhs4rdK6JjWG1+dFEhbth3EiVMXrTbDvoz4fKHDfbJWCcf77Asf4MixcyCDmfN/w09L11vLquI4riP/ncXaDbuVrd+yFxcv30BUdLRKlxchkNIERJClNHFpTwgIASFgg8DGv/djxPiFCA19YCMHVBrzMK9pJgqkFX9sQ81G3dD2vRHo3m8qXmjaE291+gzXb9wyzerwcei9h6qePoNnIZOfD1q9Vg83boag3QejMGrCt6CosVbZw4dh6DtkFho0763s1Tb9sffgccxesFyd6/E7dh+xVtxq3B3No0fPni6g9JDilCLVaiErkcz71aLVoHjr0H0sFvzwhxKcE6f/jFdaf4J6TT7C5m0H4ghZK1VJlBBwKgERZBY45VQICAEhkBYJUNwMHv0VOr75CvZumocjO77B6sWfI0KbvmP8g4ePEjyslWu24fipC1jyzUgM+/QdtG7+Ar4Y/xGmjP4Qq9ftxOFjZ63W6eXlgTYt6uPTj9op69/rTUwa1R1jBn+gzvX4ooXzWS1vLZLTotPnLsX4L34w2sDP5mH0pO9w//5Da0XixFFAjp3yPRZo06czJ/TGrnVz8OP8oRgztBP++OVz7N4wFx3eeBkfD56JdZv2xikvEUIgOQmIIEtOulK3EBACQiCBBIJu3cGE6T9h2LgFVo1pzGNaLacEFy/biOpVnsb7bzeBj7eXSn6qYG4M/PgtHDx8SrPTKi4hL4e1qc/yTxdDwfy5zIpVfKY4Mvv5IiQk1CxeP3F3d0fVyqXRqH5V5M8biLUbdysR9YUmqE6cvoSaz5VTablzZtOLxBuWLFYAvy0ajfXLphitU4emyJMrO3x9veMtzwwUkH/8tRPjhnVG7erPwN3N/COQ3N5r3wTvaKJs+rxfcdvG+FiXE0yqEAJmBMzfjWZJciIEhIAQEAJpgQDXTIWE3EPJ4gWMYkzvd/48gciaJROuXg/WoxAWFoEvF6xQgo9TfsYEi4NiRfLjxOmLoHfKNOnCpRu4G3of3o+Fn2ma6fFfG/fg7W5jkC0gC2ZpHqm+H7bB3zsOqinVC5euq4X+FJ7sy4MHYaZF4z2mCD16/Bzy5ckBP1+fePMzAwUkWZQqXpCnVs1gMOCZp4vimsbrxs3bVvNIpBBIDgIiyJKDqtQpBIQAIAwSRSAwuz/69WiLEf07WjWmMY9p5d5enggIyIwLF2/EWdcVcvceOF2ZM0eAaRGHjltr0470cP2v/WBMnrkY9C5RQL3bYxwav1gdVSuVtlkP15H99Ot6tHi1jvLSlSpRCPVqV1JTl6H3HuCffcdslnUkIejWXRz57xwqli/xJHsMEHInFEHBdxAeEfEk/vERBSSF5OVrQY9jrAdXrgUje7asCMzhbz2DxAqBZCAggiwZoEqVQkAICIGUJMApwtca18a2fw5h+R9bjU8K3rp9F2MmL1JTjvT66H3y9vZE547NQNH3fI3yenScMEtmX8yc2BtDP+mA3fuPYeLMn3FVEytfjOup4jw83OOUcTSC04PvvvmK6gP74ufn2LSjXv8/e/9DdEw0alYrp0eBC/Y79ZqIxq9/YnWKtkK5YqhQrrhicvlqXFHGByO27TqE6XN/xevNX1CizFi5HAiBZCYggizxgKWkEBACQsDpBO49eKie8tOfIrQM+QQg81g2XK92RfTp3gbDxy1A5brvo17Tnnj+lR64GRSCsUM7IcA/s2URh84pnJo0qqEWv3P91typfVFZ80rd0jxU3F7D1l5fXNfV9n8N8MuyjWCfKHT+3PAPeg74Alky+2netVIOtW8tE58a/XLhCrxYr4pao6bn8fHxwuIFI7B7w5da/XG9d5zaJItcgQFo9L8+eKfbWMyY9xt+/3OH2s6j6RsD0Ln3JLWwv0Pbl2AwGPSqJRQCyU5ABFmyI5YGhIAQEAKOEciseaS4vQS3h9CfJuSeYTT9nGnMw7ymtRoMBrRr1RB/r56BaWN7YGDvt7D46+FYtmg0EvI0I+uMiIjEkDFfoUHz3qjRqBvK1uhgZtUbdVWCr8en00BPFctYsxdfqIJfvx2FiMgotU3GlwtXounLNfHTV8OQO1d2a0XijeOTkrO+Xo7o6Gi8nQjRxGnIVs3qgl7FMiWfws3gEOX9o3esQL6c4EMCLZvWQVK8f/EOIsEZpEBGICCCLCNcZRmjEBACaYIAt4qgF8rUmrxYHTTTOB4zr7VB0RNWr3Yl9RRj2TJFEiUsPD098Ppr9dQWFWOHfoC/fpukvGw+3l6YN7UfDv79tdpWY9PKaXj/7VetdcMYxwcDxgz5AGuWTFDi7J12jZE5k68xnQdcZL9s0RiULV2YpzaN69IGj54PetrGD++CfHkCbeaNL8HT0x2vauKQ07a0If06WPWqxVePpAsBZxEQQeYsklKPEBACiSYgBZ1HYODIuWoqjgv5k1Jr+bLFlKijuKPwyZrFD9Bm8Py1qU+PBKwd45Rpw+Yfm3nYLD1uFZ5/V/O4faR22YeN/7jL/+sdh2HrzkOYM7mPehLSRlaJFgJpkoAIsjR52aTTQkAICIHEEahRrRzWLp0IeqUSV0PiSnHtFj1q1ozr0vyzZLJZMacTz164Ck4xcgq2YrniNvNKghBIqwScKsi+//k3fPvDEjPTwRw8dNQsnvkYp6fz3NL0tLQfpp0RcG+f3fuOqd+qSzu9lp4KgbRNgJultnhrkFqz1aB5b7Nw1V87QbOM5znLsGxCRs8tMnJk90/UVGZC2rHMSw9bzsAAWLMA/ywwuGnuN8tCj88NBgNeql8NE0Z2TdRWFJzqNP0ppwEj5+HRo3B06T3RjDXX53G/NnriyJf2828bHvdCAiGQvAScKsjOnD2vFkomb5eldmcTSOiP8vLHd8+cuwLTp79OnbkcZ/8jZ/dT6hMC6ZUAd6zv0amlWrOl/6yQHk4Y0RU0/dw0ZBmWteTCPbi4FxenC21ZyJ17Geb3Gi1/yolrxvjzT1w3ZsqTP+3EeD4QocdXtbPXmiV3lziXTqRZAk4VZKSQ3kQZnCXFmQAAEABJREFUXeWnz17G2CmL8Grb/urbVKdeE5UY4Z43HDONO2V//f1qLF25macpatxPh/07dvKC1Xbv3L2PDVv2qT6biiju0G06BquFTSIpxFZr39ZrNuqGFu0HY87CFaCYY9iywxA817ALfliyzrgHkklRORQCQsAOAf+smVC/TmW1ZqtR/aoOhyzDspZVHzx8Wu3Fxa0vbFmvAdPx8FGYZVGb59xUtVD+XOCCf5uZ7CR07zfV5jqy1h2HgQLRTvF4k/LkzgE+PRngH3d7Dz5Rqf+UU0L4Mm9Cn1CNt6OSQQjYIOB0QcZ20osoo5t78Oiv0KzdQCz/Y5tac1G7enlw5+veg2agVYehoKeIY+ZU35ZtB7F3/3GepqjxRrZkxWb1Ux/WGubPniT1R3kpTBf+sAaDPpuHT3q+gb0b56knpsYM7aTCfZvnY+TAdzF51mIwX0xMjLWuSJwQSCoBKR8PAf5NHtnxjXoK0l64cNYAh39yiE3WqFoWvy0ajZLFCvDUzMqUKqy8eNw2wixBO8mePSsWLxgOa2vHTOOSuq6tdIlCGND7LbUvGadlu7/fAm1bNtB6IP+EQNogkCyCjENP66KMTyhRdK1Zvwufj+iCbWtmYtJn3UFXN/f2WfvrJPj5+WDq7CVqLQLH7KrGGyhvpOuXTYFunTo0VfvtcPNGR/pNL9z3i9eiX4830LJp3TjrT9zd3MDNI4d98g4WaJ7Cs+evOlKt5BECikBQ8C30HzIGE6bOVufykrYIcNrUlrfO3c1N7Xhvbe2YaZwz17XpHjE+KZq2SEpvMzKBZBNkhEpRxpBW4Zmn8Xa7VmbGOKa5oq1csx3b/zmCcUM7K6Hh7maOir/vtmBGf3w+sgt8fLzsDoHTmVzHQU9WvJ4juzXFJnJjxOBbd9Tv08XGJOyV3ryjx88hX54cDn9D5rQnF93yZ0fstVa0cD6Eh0eAAs5ePkkTAqYEjp84DYoyhhRmpmlyLASEgBDICATMVUZGGLEDYwy99xDLVm3FS/Wron6dSjZLcLdsbpRoKwNFTL+hs6H/jEmtl7urdR38TTi9DIVaw+Yf46vvVulRKqSHjj/rwT2FVIT2QiH25cIVqFT3PdRp8hGq1u+Mnv2/0D7IQrRUx/8F3Ur4j/L6aqIzLCwCFy5es9vQ7ZBQeHl5gj9NYjejJAoBEwKlShYDjVEUZiLKSEJMCCQvAandtQikmCBb/ed6bNm6M465Fo7Y3ly5ehNcyF+3VsVEPzVKUffxoBnYsv0gxg3rrNZP8CdEijyVF+9+OA5/bdwT25iDr/RqjZm8CDPm/Yqu7zZXO2ev/HGsKv3JsDmgWFInDrzwp06iY6JRs1o5Y24u7ufDCo1f/wRcEGxMeHzwVMHcaPRCVUyc+TMO/3f2cax5wI0bP5v4LRrUfRbFiuQ3T5QzIWCHQGCO7OjYvo2IMjuMJEkICIH0TSDFBBm9O9x3bLMmynRzVbSRUdHqScHMmXwS3cWVa7bhwOFTmDetn/rtNq6VKFWiEKaP74kX61UFn8ikaHO0gUOaCPr19y34qHMrTZC9pk03Bqrfp+O6tob1qjj8+Hpif5SXazL69WiLF2pXQtv3RqDl20MwacbP6kd5GbZ+dzj+p8U9W7EU+vdsF2eNmaPjlHwZl4DzRVnGZSkjFwJCIO0RSDFBRjQUZAH+WXmYro1rxrilxPM1ysf5bTb+5EjTl2vi5JlLOB/P9J8ppIOHToGPtzdu8BwMhicbKLK+V1+qYRZnWs70mKJ41tfLER0djbfbvuRQGdPyfACgxat14O3tiWfKFlVr2Dj9evfeAxQvnE/Ft2vVEMxnWk6OhYCjBHRRxpBlOH05QRb6E4WYEBAC6ZxAigoyskwLoiwwhz+yB2S1OnXHMcRnUVFR4JYZfj7eVqc8c+XMpjxaQcEh8VVlTKeY8vTwUKJHj9TDrFkyWY3X0xmyP4NHz8efG/7B+OFdlIeN8Ym1erUqgpsq8qlTGvfrSWxdUk4ImBKgGKtZvYoxKjj4tvFYDoSAEBAC6ZVAigsygnR1UcYF6XVrV8Qf63Yl6mlBAwyaEHPDg0dhoDiDxX+3bt+FwWBAYI4AixTbp/SE0bNFs8x1N/S+3TVkXNv1esdh8qO8luDk3CUJbNuxGytWrTX2rWP7NsZjORACQiBVCEijKUDAaYIsIiISdWtXj2OMtzYOirLTZ84Zkyo88zQszZiYwgcGgwFtW9THvfsPQa8Sn5a07AK3r6Bg41OUlumcsqtcoSR27jmKo8fPmxWlp+u33/9Gwfy5wE0UOf3HjRPPnL+qvGZ65stXg3Ds1JOd9ys8UxxsZ9O2A3oWFbK+3//cYVZWJTx+YT/PXriKMiWfwrJFo1GxXPHHKRIIAdcjwG0vFnz3s7Fj/Xp1NS70N0bKgRAQAkIgHRJwmiDz9PRAHU2QWRrjbXHLkSO7MclSjPHcmJgKB8WL5lc/ZPvfifNqAfviZRtx5VoQuE3FgUMn0ePTaeCP1bq7u8FLG7tlF99o2QDcLLHXwOnYtusQwjXBeiMoRP0E07rNe9Ht3eYI8M+MLJn9wM0LuQHtuk17VT56tAaMmIt79x4aqy1Xughefbkm+KTlkuWbwHVq3NeMP5m0fPVWYz7LA4PBgJeS8KO8rG/8tB/Q4PEPHnfpPVFthMsf59XjGPLc8sd6WY7lxYSAIwQoxiaYrBdLUTHmSAcljxAQAkIgGQk4TZAlYx9TrWr+VMhyzatEwTRi/EK82KIP+Ltwb3b6DFxkP6hPe3w26H2ri9izZ8uKr774FMUK50OnXhNRqc57eKFpT/VU4vjhndGw3rNqXAaDAR+0b4LSxQuB4o35WrQfrKVXwcsNqqk8fPHwcFdPL77WuDaGjVug9jbjvmbbdh0Gd8f38fFitmSxxg2fw6cftVPGdWNTRn8IrhvT4xjynPFM5zmN5ZKlQ1JpuiMgYizdXVIZkBAQAgkk4FRB9n63vrA0R/szffbXGDVuqpk5WjY58+XOlR2TR3cHf6tx08ppoPFnlLasng4+UUihxPb9fH3A34bj78jxnMaHA+ZO7Yeda2ercn9rZbavnQUKFYPBwCzK2MaiuYPVzzOx/t0bvkSXjs0wcVQ3mNbHqVD+XiTTmY/1rVo8Hq83r4e9G+ehXu1Kqj4rL3aj8uTOgVbN6oIeO2sZKUgb1a+KhBrLWatP4oSAJQE+TanHiWdMJyGhEBACGYmAUwVZUsBxTZkrb4nBH6vlXmI0CheD4Ymgim/cWbL4geXoNXN3s47cYDAoQcR8FHew8x/Tmc9efXaKx0mSH+WNg0QiUpgAd+nn4v1xowbKmrEUZi/NCQHnEpDaEkvAujpIbG1JLOfqoiyJw0sTxd3d3VG1cmm1ri1NdFg6mS4IcKuLWjWqgmG6GJAMQggIASGQQAIuJcjYdxFlpCAmBISAqxKQfgkBISAEkoOAywkyDlJEGSmICQEhIASEgBAQAhmFgFMF2fxZE2FpOshmTRrFSWOcnm5ZrkfXd/UkCVOUgDQmBISAEBACQkAIpDQBpwqylO68tCcEhIAQEAJCQAikUQLSbTMCIsjMcMiJEBACQkAICAEhIARSnoAIspRnLi0KASGQMQjIKIWAEBACDhMQQeYwKskoBISAEBACQkAICIHkISCCLHm4ZoxaZZRCQAgIASEgBISAUwiIIHMKRqlECAiBjERgx74LEBMG8h5IufeAK7FOrnudCLLkIiv1CgEhkG4J1KhcCGLCQN4DGfM9kFw3NrfkqljqFQJCQAgIAUcJSD4hIAQyOgERZBn9HSDjFwJCQAgIASEgBFKdgAiyVL8EGaMDMkohIASEgBAQAkLANgERZLbZSIoQEAJCQAgIASGQtgik2d6KIEuzl046LgSEgBAQAkJACKQXAiLI0suVlHEIASGQMQjIKIWAEEiXBESQpcvLKoMSAkJACAgBISAE0hIBEWRp6WpljL7KKIWAEBACQkAIZDgCIsgy3CWXAQsBISAEhIAQEAKAazEQQeZa10N6IwSEgBAQAkJACGRAAiLIMuBFlyELASGQMQjIKIWAEEg7BESQpZ1rJT0VAkJACAgBISAE0ikBEWTp9MJmjGHJKIWAEBACQkAIpA8CIsjSx3WUUQgBISAEhIAQEALJRSAF6hVBlgKQpQkhIASEgBAQAkJACNgjIILMHh1JEwJCQAhkDAIySiEgBFKZgAiyVL4A0rwQEAJCQAgIASEgBESQyXsgYxCQUQoBISAEhIAQcGECIshc+OJI14SAEBACQkAICIG0RSCxvRVBllhyUk4ICAEhkIIEgm+FYPuuvWCYkGaZf+fu/Qi9dz8hxeLkvXjpCvbs/xfh4RFx0mxFREVF4dCRY8p4bCufxAsBIQCIIJN3gRAQAkIgDRA4ffYcps3+GgytdffAoaPo3mcIGJqmM/+XX3+P6zdumkYbj2NiYnA39B5u3Q6JYw8fPTLm273vXyxc9Avu3Y8r7ELu3MWQzyZizbpNxvw8CI+IwJLlq5XxmHFiQkAIWCcggsw6F4kVAkJACKQogS/mLECbd7rHMcY70pHw8HAEBd/SPFjhjmQ35nkUFoZJ0+eia+9BceyPteYCy1jI4iA6Ohq3b9/BgwdPBJxFFjkVAkIgHgIiyOIBJMkZj4CMWAikBoH32rfB7CmjjTZ57FAULVwI7u7uDnXnwcNYMRQVFe1QfstMpUsWw8I5k/DzwpmqDzlzZLfMYvOc3rX7Dx4qD5vNTJIgBISAXQIiyOzikUQhIASEQMoQyJTJD9mzBRjN3c0Nt0PuoEC+PPF2gOuz9h88rPJt27kHkZGR6lh/efDwIQaNnICOXfvi1JlzerTTwuMnz4BtnD57HqHa9KfTKpaKhED6JmA2OhFkZjjkRAgIASHgGgROnD4LTieWKlEs3g7t2nMA+w8eQY1qlXHkvxPYvG0XuDZML+jr64NPe3fF5LFDULhQAT063nDXnv2YPf87ZTy2VuDGzWD8teFvFC9aWE2Zrtu01axta2UkTggIgbgERJDFZSIxQkAICIFUJcDF9Os1YfNUwfx4qlB+s75Mmj5PrTP7Z+8BcO3W5q27MG/hjyherDDe79AWL9Spga++/Qlce8Y1ZSxsgAFZs2RGtgB/eHh4MMopRg/e9C8XKu9Yp47t8EqjF/DLstVY/OvvCOfTmE5pRSoRAhmDgAiyjHGdZZRCQAikEQL0bK35axPOnruoBI6vj49Zzzu/+6Za41XxmbLg9OSXC75HmVLF0bv7+8icKRPeatMC77z5Oq7duImo6MStJ9MbfK5KJXR9v70yHuvxDA8fPY5+g0fj0uWr+OCdN0Dx2LRxQ7zcsC6WrVqLb35YguhErmdj/WJCIKMRcKogGzVuKmzZ5q0747BlnK38k774Mk5+V4j498hp7N53DFyz4Qr9YR/u3L2PLdsPgiHPxVKMgDQkBJxKgGJsw5btWLr8DzX9+GzFZ+LUn/nxWjMvL423TbcAABAASURBVE+VZ9Lowej7USdkyZxJ5XVzc0Oj+nUwdtinyJ0zEF5eXsiRPcCpnjE2xIcA3mzdAhM+G4iqlSswSrXx9hstMXPSKLzZpjnc3J36EaPakBchkF4JuORfi5+fL/47dtLlmFOEff39asyc/xvCHHDH79h9BA2a93bIfv5tg83xsi22u3TlZqt5Ll25iRGfLwRDqxkkUggIAZcnwCm+b39civnf/IQK5Z/G2+1aKYFjr+OcfsybJxfcNBF24dIVTJ4xX+1F1qHLx+j0UX/lwTp34RJGDu6D+NaO3bkbil2796vNZ7kBLNevxdc2p0e9vb3BjWe5cayenw8n+Pn66qcSCgEh4AAB+4LMgQqcncVVxRjHefb8NezZfxzHTl3A+YvXGWXXcufMhk8/amfXunZ8DfcfPMK9ew9t1kUhuGXbQezV2tYzUaTdDAoBLeROKGKiY/QkCYWAEEhjBC5fuYZPho7BmnWb1ZRfzy7vIpP2xdTRYXAH/8EjJ2he8lA0f7UROnd8E5y25DTjug1/qycsg2/dtlqdm8EN/lmzIiIiUq3/+n7xMixf9RcotPz8zKdLrVXADWe58Sw3jrVMd3dzB6dWaTy2TJdzISAEnhBwKUHmp92AXNEzRlwnTl1Er4HTUadGedSvXQm9B84A45hmy4oWzqdNHVS1a3VrVURmbdy26rAVv+Ofw6jXtKeyTr0m4k5o3N2zbZWVeCEgBFyLQO5cgaj3fA2MHzkAHTTPGKcjE9JDerS4+L9/76548YXnUfO5Z5W1av4Kun3wNoKDb4NbUlir09vbCx9/+L6aZuRUo6m93LCetSIOx3EcLZq+BBqP7RWUNCGQ0Qm4jCBzRTFGL9SBQycxYORc/O/tIahQrjiG9OugrE7NCmjZYYhKYx7mtXwzOTJl+XrHYbh6PdiyqNl5WFgEboWE4sGjMOPatXqaKDyy4xvQFi8YgQD/zGZl5EQIpCUCfBqw/5AxmDB1dlrqttP6yqnH5k0aoVCBfImqM2dgDly6fA07du8Dn9BkJVyPdv1mEP74a5PaXJbTiIxPLrtw6bKa7qS3ztI4pZnU39JMrn5LvULAVQi4hCBzRTF28swl1H31I3ToNhZcn7Hyp7EYPfh9rF63U9nAj9/Cih9j05iHeVnG9MKGhYWrp4xmTeiNn+YPs2q/aGJq08ppeKNVA9OiZsfnL13HBc3+PXxaE2+3zNLkJK0QkH7aI3D8xGm1hxVDCjN7eSUtLoGWzRrjpYZ18O2PS/FOlz5o8053tO34IT7qNwyXrlxFnx4foHjRwnELOjFmxz/7MG3211bty6+/B6c2ndicVCUE0h2BVBdkrijGeJWLF8mP9cum4MCWr5QQK1IoL6PVOi59LRfjKNKYh3lZRmUyeXF3d0f2bFmRMzDArvn5Wl+rERkZhV+WbULVSqVVPb/9vgX85mvqfevSeyJCQx+YtCqHQiBtEShVshho7LXuLeOx2BMCXIfFn1Zi+CQ29ojTgW1bNsOCWRMxb/p4tS0G8y6cMwlTxg5FuadLxWZMwmvjRvXw2dB+mjc+q1ktFHoLZk9UP7n088KZVkOmM59ZQTkRAkLAjICb2VkSTli0Tu3qsGXWnvApWCAfShQrgmaaq96asc7UsMtXgzBu6vf4/IsfMXz8Qgwbt8Boew4cB800briWh3lZhmVN+xx06w4mTP/JWN60nOkxn6K0nPak8Prmpz+xZt0udOn4Gjq/0wwLf1yD5au3otIzJYwet3HDOyNzJl/TZuVYCKQpAoE5sqNj+zYiyuxcNYouTjsytJXNYDCoDWCZj2a5h5mtco7Es64A/6xqxsCR/JJHCAiBhBFwqiCrqwkyW/aUlZ/rKFq4kE0xRoGWsKGkTO4a1cqB5khrRZ7Kh8+Hd0HDus+illbOnj1Tpig83J9cjnv3H2LM5EWYMmsxur3fApUrlEDDes+i23stMHj0VxirCUb2gZ63AP8sMLgZeComBNIsARFlafbSpXTHpT0hkC4JPFEA6XJ4iRtU/ryBGND7LXCd2IeaGHLEmJdlWFZv9amCue0+Ydmo/pMnMKtWLq0W3rIsd9f+Yck6LFmxCWOGfIB332wMg8GgjMcTRnbFhYvX1M+mML+YEEgvBHRRxpBj4vRlRl3oz/GLCQEhkHEIiCCzc61Nt5bQt5iwFTKvXtWJ05fQ4q1BDm0Ia7pxLMuwrLubG95r3wS7189Fs8a1lBDT6zYYDGjc8DksmDkAuXNl16MlTE8EMvhYKMZqVq9ipMAtG4wnciAEhIAQSKcERJDZubCmW0twewlrtmnlNOTNncOsFm4I26NTS6sbwtKDRrO2YSzLsCwrc3dzg4eHO27dvov2XUbD3k7+kP+EQDoisG3HbqxYtdY4Iq4tM57IgRAQAkIgnRJwqiDjb1PaMj7O/pihMWAcb7y2zJgxlQ6OnbwQ72J8Ltjnwn3TLvpnzYT6dSpbna4skDcnaKbTlfoxy7CsaV1RUdG4ei0Y9nbyL5AvJ4Z98g4YmpaVYyGQ1gjwnrDgu5+N3e7Xq6txob8xUg6EgBAQAumQgFMF2ZatO2HN9uw7iOMnT8fBxzhbYozxcQqkcMS168HqicaHD8Nstuzr643XXqmNPBZeMpsFkiGBIo4b1TJMhuqlSiGQIgQoxkzXi4kYSxHs6bwRGZ4QSDsEnCrIrA3bVfcZs9ZXa3GB2f3Rr0dbjOjf0a6VLlHIWnGnxT14+Ej9biV/u9KWhcpeZE7jLRWlLAERYynLW1oTAkLA9QgkqyBL62KMl4s/a8SF/GVrdIA9e6fbWFA0sUxy2JwFK9TvVrIvtmzslEXJ0bTU6cIE0kvX+DSlPhbxjOkkJBQCQiAjEUg2QZYexBj3G9u0chocsalje8DXxzve907blg1Aizfj4wzcZ2zdssnqNyutPVRgGjdmaKfHpSQQAmmLAHfp5+L9caMGypqxtHXppLdCQAg4iUCyCDLniTEnjTKR1Xh7edr9uSOKJd0C/DObbU9hq8nyZYuBZitd4oVARiTArS5q1agKhmlh/GFhYRATBvIeyJjvgeS6RzldkKUXMZZcwKVeISAEhIAQcEEC0iUhkMoEnCrIRIyl8tWU5oWAEBACQkAICIE0ScCpgqzPR50xf9ZEq2bttykZZys/49MkUem0EHBNAtIrISAEhIAQcGECThVkLjxO6ZoQEAJCQAgIASEgBFyWQPoRZC6LWDomBISAEBACQkAICAH7BESQ2ecjqUJACAgBISAEzAjIiRBIDgIiyJKDqtQpBISAEBACQkAICIEEEBBBlgBYklUIZAwCMkohIASEgBBIaQIiyFKauLQnBISAEBACQkAICAELAhlSkFkwkFMhIASEgBAQAkJACKQqARFkqYpfGhcCQkAIpB0CN4JCsGnbAdy5ez9VOs12t+48lGrtJ2LQUkQIOExABJnDqCSjEBACQiD9EoiJicGVa8HYuPUADv93FuHhEXEGe+zEBQwcNV/LFxQnzTLi7Pmr2LbrMMLC4tZjmjc6Ohq3bociKPhOHAu+fReRkVHG7FeuBWH05EUOtZ/a4tHYaTkQAg4SEEHmICjJJgSEgBUCEuUUAot/24gvF67Eg4dhVuujqFnwwxowX1RUNJat2orPJn6HPzfstppfj9x38KTK9+1Pf1oVWHq+K5oQ6/jheLzadgD6DJ6Ft7uORd2mvbFq7U5QqOn5EhJu3nZQiafQew/sFqMYe6vLaDRq2S+ONX1jIE6euWS3vK3EhIhHW3VIvBBISQIiyFKStrQlBISAELBCwN8/M77+/g+cOHXRSipwXIufs2AF3N3dNXPDvn9P4tff/8a8b39HyJ17VstQxH31/WqV7+8dhxCpCTlrGTkN+OnwL7V63bHyxzHYt2kudvw5Ex3aNsLw8Quxa+9/1orFGxeleb5CQx/gVkhovHmZ4aNO/1Nts33dtq+ZgTIln2Jygi0yMhKPHoUr71uCC0sBIZAKBNxSoc201KT0VQgIASGQ7ATKlSmCbJoo4xSftcZ27D6i0qtXfdqYbDAYcO7CNRw9ft4YZ3pw5vwV/Hv4NAwGg2l0nGNOT546ewU9O7dE/ryBKt3b2xMd2zVGtWfLYM26fxLsJaOnb+fuo7j/4BH2a+JRVZqCL/QibtWmS9kk15wl1svH8mJCIKUIiCBLKdLSjhAQAkLABoF8eXKgepWnsXHr/jger7ual+nvHf+iUvkSyJMru7GG0iUK4elShbFyzXZQgBgTHh9s2f4vcgYGoErFko9jrAcnT19CtoDMYB9Mc1CU5ciWFZevBuGh5mkyTYvveJM2jrMXruKl+lXx/S/rwCnR+MrM+3YVGrf+1MwmzVysPHTPvtAZlet1wpudRju0oP/fI6exfvM+vPZKLfyxbheOHDsXX/MukC5dyOgERJBl9HeAjF8ICIFUJ2AwGNBIEy8XLt1Q05OmHfrvxHmc0ERT05dratOKT27Zfr7eaK4Jjp17joLix7QMF8NzfRkFUW4TEWeaRz8uUawAHj4MQ8hd86lPTnmyngBNrHl7eerZ7Yb0RK3duBvDxi1E+9aNMKD3m8ined0+GTYnXlH25usN8d3sgWbWqcOrqPRMcfy55HOsXToBMyf0RNbMfnb7cFDzCvYaOBMv1nsWn3zUFg3rPot+Wvsiyuxik0QXIPDkr9sFOiNdEAJCIP0SkJHZJ1CqREEUyJcTm7YeME4RUuDwnPFMt6zhmaeLgmJp74ETZkl79h/H7ZBQNKhb2Sze2gnXaAVm98fYKT/g+s3bKguffFy6couabny1UQ0zIagyWHnhWrTPv/gJA0bOx/vtm4ACK2sWP4zo/47K3ea9EcpbFWny1KRKePxCgRmYwx+mlkUTX16aGNTjArRpXYOb4XEJ8+DhozDwwYcPek3E8zXKo8+HreHr441eXVvhmTJFwYcWmM585iXlTAi4BgERZK5xHaQXQkAIZHACnB6srk1bchH9LU1MEQdDnjOe6YwztXx5AvHC85XU05D37j9USZy+pIh7unRhFMyXS8XZe8meLQs+H9FZCbjGr3+KBs37oHqj7pg6Zwl6dWmFOjXL2ysOetH4ZOYLzXpj7cY9mDqmO+jZ8vBwV+Vy58yGr774BK2a1cWQMV+r+vkAA/upMjx+4dOU6zbvBY3evWlzlmLo2AXo2meK3YX5FFjjp/2I51/5CHO/+R19urfGyAHvKDHGqjNn8sW4YR+oeKbXfbUXKBxZjuliQsBVCIggc9qVkIqEgBAQAkkj0OiFKrh24xaOn4x92vLw0bO4ev0WXm5QzWrF9BY1bvgcuOfXv0fOqDycvuQ0ZjNtipPrwFRkPC9FnsqLJQuH4/u5g7RpxnaYNrYHNiyfjNbN68FgMNgtnT0giybaKmhC7EM1tUjvlMFgXob94EMD65dNRud3muK5Z8sYvW5ubm5qbRyfHOWaMRrF4PlL1zVR5YXmTWojk5+PzT74al4wCtYP5/HbAAAQAElEQVSRAzpqfZ6ENi1eAOs0LcBzxm9YPgnDP+2g2mc50zxyLARSm4AIstS+AtK+EBACQuAxgeJF86N4kfxYu2E3OLW3Zv0/KKHFFS2c93GOuEGp4gVRvlwxVYZTnOs370M2TSRVqVQqbmY7MRQtnL7kmqsaVZ8GPUt2shuTDAaDWjxPT5ruFTMmWhz4Z82Edq0aoGzpwsYUeui+nv4J/lg83swmf9ZNE4dvqgcDKOiMBawc1K1VAa+8WF0TcN5WUp9EUYQxH/M/iU2DR9LldElABFm6vKwyKCEgBNIiAYqgWs+Vw+79x9Vu+dwyokmj6nbFEcXKq1oeesW4+J9bZ3Axf45sWROEgDvlv9KmPxb+sCZB5ZyVmVOI/UfOw5IVm51VpdQjBNIUARFkaepySWeFQIYgkKEHSU/T3dD7+O7ntQgLj8Cz8WxbQVjlyxZjgC++XIoL2lQf61ARTn5hvUnZrNVed2JigODgO7h3L3YtnLW8JYoWwPdfDta8hgWsJUucEEjTBESQpenLJ50XAkIgvRF4qmAecI8x/qYkpx2LFLI9XamPnXuIcXH/jt1HUbZMERR9Kp+elKwhN4D9oOdEtUdY5XqdEhQmxhPHKdHs2bKAoT6woWMXJKhdvZ8sp9choRBwBQIiyFLjKkibQkAICAEbBLj9Q8N6z6pUrudyd4//Nm0wGMDF/d7eXkjIYn7ViMULRRanL+2Z/vuUvj5emDiqq9ojjPuEJcRat3jBouXY04S0zxL9erRJVPssx/JiQsBVCMT/l+4qPZV+CAEhIAQyCAE+Ebhv01y1oN3akPlE4bxpfUHxpqeXL1sUO/6cEaeMtbx6GWvh/O9WxfmRb8sf/p4w/WdV1GAwgAv19X3CEhKa9l1V9vglIe2zCPcqS0i7el6WY/n0bjK+tENABFnauVbSUyEgBIRAshGgUFn98zhQCMZnFHnO7ggFGkVmfG0zPTnad/Z4pD4hkFACIsgSSkzyCwEh4EIEpCtCQAgIgfRBQARZ+riOMgohIASEgBAQAkIgDRMQQebiF0+6JwSEgBAQAkJACKR/AiLI0v81lhEKASEgBISAEIiPgKSnMgERZKl8AaR5ISAEhIAQEAJCQAiIIJP3gBAQAhmDgIxSCAgBIeDCBESQufDFka4JASEgBISAEBACGYNAigmyoOBb2LZjN1asWqtCHh8/cTpjUE6ZUUorQkAICAEhIASEQBolkKyCjCKMAuz9bn3Rf8gYLPjuZyXIGNImTJ1tjBdxlkbfQdJtISAEhIAQyGAEZLjJQSBZBJkuxCjCKMjsdZx56S2jQKPx3F5+SRMCQkAICAEhIASEQHoj4HRBRkE1ceoc5QnTYZUqWQzNmjRCv15dMX/WRIwbNRAd27dRcUxjPpajMGNZHjPOlezfI6exe98xREVFxemWvbQ4mZ0UERMTg5A79/Dg4SNVI/tAUydJeHkUFo6/d/yLM+euJKGW+Iuyr9Z4ki/jmR5/LY7luHP3PjZs2YfrN287VkByZXgCAkAICAEhkNIEnCrIKKToFWPIgQTmyK5EGIUYBZkuvhhfq0ZVJciYRoHGOJZhWVcUZT8tXY+Z839DWHgEu2lmttKOnbyAYeMWOGTMa1apyUlo6IM47T58FIZeA6bjxyXrVU72gaZOrLzYEiWM37L9IBiyGNsaMX4hNv69n6dmduv2XbTvMhoNmveO18ZP+8GsrOUJ+2qNJ/kynumWZRJ7funKTfQbNhv/HT8XbxUUbRRvOo94C1hkSClBa9GsnAoBISAEhEAaJ+BUQTZR84zpPCjAKLR0EabHWwspxvr26qIEGtNdQZTxA5kfzGs37Abt0tWbCLp1B+s371PnjHOGF+nhwzAsX70V164Hc+hmdv3GLbz5wShUb9QVVV74AF9/vxpR0dFmeRw9MRclT0oxfsTnC8HwSaz1o6ioaFy9FoxnK5TCpx+1s2n58wbijua9M62FAs9UnO45cBynzl7G6EmLjIKV4wsLiyt4TevRj+kZfKfbWJSt0cGqffXdKj1rgkKKNoo3R3hYq9ieoLWWX+LSJgFvb2+ICQN5D2TM90By3bWcJshM139RjNGsdZqL9ym4LNMoyliGxjTmWbn6Lx6mitFTMn3uUoz/4gdlBw+fxvmL1zBl1mJ1zvjd+4/Z7VvpEoUwon9Hu9avR1sEZvePUw89LSM//0bF//rtKAzp10F56LZsO6jiUvOlVPGCaFS/qk0rkDdnnO7dCrlrFlejWjk0qPssPDzczeIdPfH18cbUsT2waeU0M/vjl89RoVwxR6uJky8yMgqPHoWD3sA4iQ5ERGuCmXb+4nUHcksWISAEhEA6JyDDc5iAUwQZRRbXf7FVXVjx2NKYb8LU2bAntGpWrwLdq8b8NMt6UuK8ZLEC+G3RaKxfNgXrfpuMl+pXQ5Gn8mGpJo4YR2vTon6Su3IjKAS374TGqYdTmFxH1a/nGyilCbvXX6uHFq/WweJlG+NMX8YpbCeie7+pZh6l1h2HqbVolkWOn7qoPIFbdx5KUnt6vS2b1lXCdOgnHdCh7UuopQkyWmttXEP6vq3S3n3zFc3r4KkXsRsaDAYE+GdGzsAAMwvM4Q8vT8fqsGyA69f+1DyijP9r4x6r6wWZZs8OHT0DXtN9/55AsOZRtZdX0p4Q4BcwLnfg/eFJrBwJASEgBDIOAacIsu279hiJcbG+8SQRBxR0eh28Sa9YvTYRtTi3yOWrQdijecPOnLuCvdpUm3Nrt17bCU0Q5dWm/oo+lVdlMBgMqP5sGZw8fQl3795XcYl5mTmhF47s+MZoixeMUMLGsq4Nf+9TnsBlq/5GtDZVaZquizVO21ozTu+a5tePQ+89RLc+U/DamwOxYs02/LnhH7zX83O07DAEV64F6dlU+DAsHDeDQpSnKrHTtKqiBLxs2LIfHPfbbV7Cqr92gOcJKK6E7bxvf0fdmhVAT9uvv/8NPnyRkDoyal5+8eLfO0MKszTEQboqBISAEHAKAacIMt5E2Rsu1Ne9WzxPrFGU6fUEB6fuk3H8YOWHbIH8OdGuVUNM1qYsL1xy3nTU3dD7yqOTMzCbGa6QO/eQJZMvPD08jPF5cudAmCZUVvyxTa1l45o2Y6KTD7p2fE15ByeO6gZfX29Vu7u7G/LmyYG9B48rscZpW2tGAeuvea9UIZOXb39ao6Z91yyZiBmf98Kkz7rjr18nwz9rJm0q+BczjxSFXr2mPdG643DcunXXpJYnh0tXbjauP9PXp3FNGtemPckV/xFFE5l+Mnw2ur3XAr27t8ZrjWtjwKi54No3piOe/7jmsPegGQi99wCD+rZHn+5tMGfBcixa/Fei1/3F02S6SubfO42DojATUUYSYkJACGQkAkkWZBRjvIESWo7s2Rg4xUqVKKbqYd1sQ52k8AsX1fcaOF15cvr1eAM9OrWMnT58Zxh+/3OH8oJY6xJFHKer6OGJz/47cR5eXh7QHGBgGZZlnZcu30TunNmMYohxBoNBTR8u/OEPTcAsVuKG8QmxfQdPqqlICh7azt1HEB4eabsKk5Ts2bLiuzmDlFDjlK09+7RnO5OSsYeXr9xE5fIlwEX/sTFAlsy+mkepovKGhZk8wfpa41rKi7du2WQ1JannNw337j+uCdO9ZteBa9Ia1H0WJYsXNM1q9ZhC6/TZy+jx6TQMHDUPnd95TU2nenl6YODHb4FT0kzj06y2FvnTe7f9n8No8+5w9cDDDE1o5ssTiIb1nlWibML0n/DxwBkOPTRhtZMZJJJfwugZF1GWQS64DFMICIE4BJIsyCiY9FqTQ5CxbtM2eJ4S9sdfO9Gg+cdKKPw0fxgKF8yjPDhjh3RCp3eaYdBn8zBxxk9Wp6Q4pdeoZV/U0zw88dmkGT8jKPgOXn9nGFiGZTm+pwrm1qbxgo37jDGO3rGsWTLhm9kD8fvP48CnHRnviHlqIqNQ/lxqKs7Uq/XD0nUIzJ4VTLdVD9dWcW8wCriEGqd59Xrz58uJf/Ydw6kzl/Uotd3Gpm0HULxYAXChvjHBwYPiRfJjUJ+31Bo00wconq9R3m4NoaEP8O6H49Cs3UCcu3ANX33xiSbImhofMvDwcEffD9uo+NPaVPVL2vXs8vEks+tBUV6vyUf4oOcEPPN0Ufz89XAULZxPtWswGJRH9Yd5Q6CXf/ODUTh74apKl5e4BESUxWUiMUIgIxHI6GNNsiAzBah/uzWNS+xxjhxPvG3Bt1J+2vKFOpWx/PvR+GH+UBQulAdjpyxS+35Fx0TjvbdewT/rv0Tvbq01z5YhzhDLli6MvRvnKQ+P6Xqt+I5ZhmVZYe5c2cGpv9B7D3mqjFNxfn4+yBaQBQn9r6QmePSHFCw9W4xnuq06wzUP2s+/bbA6TTlqwjf4ePBMMDQVevqx6ZOob7d9GRWfKY7mbw0ChWr9Zr1Qu3F3tUbtg/ZNrLK01aekxmfJ4ofBfd/G2l8nYeWPY/FcladV+ydOX1J7rTE0GAwqnunM169HW/j5+hib5tOc77RrrDyGE0Z2VVOvxsTHB+XKFMHyH8bg+7mD8VLDasibO8fjFAmsEdBFGUOmBwXfgiz0JwkxISAE0juBJAuyxIglTkHyRmsPrn5DZh5net5YnyPm4+2FYpr3xd3NOiJvL0/Q7NXF6Udun8DQXj5raU+XegoRkZHYd/CESuY2GOs27VWeGD5dqCKT8EKht33XYXy1aLVah/Xj0vXguY+PNzhN+J4mkPTquYaMa8nWL5uixIdpOG3cR0ogzpnSN04a83HaT6+H05OsZ/Pv0zD803fUWiuuJ1ukiRUKUD2fs8IwbQqU+5XZqo/Xl9OnBsMTUR0REal5JoPAUC9nMBjUNCvz63EMC2oeR3LKkzs7T22au5ubJkRLgA8L8H1lM6MkKAL82+fT1upEe0ntdaRaF5z0T6oRAkJACNgmYF1t2M4fJ0Vf68WE+G6c9Hpx4T/F2MSpc8x+XonlTU3fRsM0LqWPOa2lrwHjU3/hERHq53coXP7QpjQ53cjtKWz1i9OPr3ccBoa28tiKL/JUXrzcoBoGj56PKbN/QY9PpoFbKrzV+kXlybFVLr54CrFPhs1BjUZd1bTr0WNnVZHt/xxGnyGzUP3FLpg8c7HZuiyVQXshDz7UwJ9W0k7Vv7uh982m8VSknRd6/eZ+sxJ5NE9RgzrPKqFjMDwRRHaKWk2i15AL+YeM+Qr/e3sI+CsC9L6VrdEBleu+b/wlA6uFJdIlCfBv3/Q3cLm2zCU7Kp0SAkJACDiRQJIFmWlfjp88bXoa55jffHlzpTGRN93+Q8ZYFWamnjdnToWy3fjsdkioWlvEHfL54U7j2iluDtvsjQFKJH3781q1wD6zn2981SUq3WAwoFfX17Xp0Sb4c/0/oIds1sTeKFPyqUTVpxfik470ui39ZiQ2rpymnnTk2qvp43ti+58zMXdqX/yyfBP4BKNeRg/Zh9Vrd4JbcuhxpqEjDRi/XQAAEABJREFUx3x6dMmKzVZ/mYDl6XXs/n4LtG3ZgKd27dlKpYyby3Ih/puvN1S/HjCk39tYvfhz7Fw7G/Rg2a1EEl2KAL3n3GRa71S/Xl2N+xLqcRIKASEgBNIjgSQLMnq9dDDxCTI9H71kfR//VBK9Zbow09MZmgoyCjnGpZRxSvDb2QOxbc1MHN6+0Gwt2KFtC7FhxVT8OH+oehKvQP6cydYtTm91e6851iyZoJ5urFS+RJLbUk86Vihp9SlEg8EAtsGd+A8eOuVQW/VqV1Lr5fS1bw4VspPJ3d0dVSuXRvmysU/Z2skKfbNZCsoh/Tqo80b1q4KeNz4UwXVitsoPHDnXbINcetRo3Cj32vVbYMhzS2M51rlp636r5S3zW543fPygCOsQMydAMTZh6mxjpIgxI4o4B9w0mg/a8IGbOIkpEMFtXkx/AzcFmozTRExMjNr7j8sSyIE8TB8iilMgGSPIY8OWfWoGJRmbkaqfEEiXR0kWZBRLugeLU5a8qTpCiuX4M0njRg0EBZqZsDtxGpy2YD1MY5iSZjAYQFFGMxgSP53GPsdE86YRqp7W1Kc/rYX0HPEGwzLJaRWeKQ5ufsonBC3Xtj18GIZfV/6NQ/+dwYsvVLXZDd4ArY3BNI5r57glhK1K7oY+iJcJ14DZKp/UeHrgpoz+EAk1lmPbNaqVwybNw5hQW7xgOLJnz8oqxEwI8L4hYiwWCP8uj/x3Fuu37MXFyzes7mP309L16qfU4vsb0YUKBVxs7bZf+ffKv1vTv2P92HRLHtbAbWBGfO7Yb+BSJHGZAz3sLOuoMT/LcXbC1Ci8OK6Hj8LUg1Y/LlmvZitmzv8N3DfQtP6EfnFifr0822Bbpm2bHvPn9fS85MHfwOVv4epxEgqBhBJIsiBjg/oUJL1dptMNTIvPKMxYnt+G9bymu/PXfK6KHp0mwzuh99Gp10T1VCGnPm0Z97riDcbRQdKTVKdWBaueLnt10Kv0oTYlOHzcAlR4/l083/hDte6KYZX6nfDlguX4bND7qFe7os1q5ixYEe947G3oyooHaB4qWyz0+B3/HGbWZDF64OhNS6ixHDvEqdWcgQFqj7SEhNzLzd3NKX927Ea6Md479MHwXqB/ydPjMkLIL2Sbtx1ArZe7o/W7w/HRp1/g5Vb90OrtIaCoSQwDCjYKFQq4+MpzA2b+3ep/f6ah6ZY88dVjmU6RNGL8QoRqX8Is0+ydMz/LcdNn/althnziOzw80l5RY5r+xemPXz4Hn4ru0rGZ2RcpnufS/o5//XaUimd+vTDbYFts09TGTFkEbgIt4ksnJaGzCDjlk4GiSvdk8caaUFFmOhhOX/LbMuNYZ1q4Mbdt2QBc98QPafZbN07j7XVw+4uFswaYbamg12ErZFv87Ud9vy32gWYrvx7P/bW4VcOejXPVlOysSR+rdVcMOUW7ZfV0NG74nNUHByg8+ARmfNt3MJ35mF9vVw8TwqSeNh2ql0tKWCBfTkwY0RVlShVOSjVSNhkJ8O+cX8zoMedxMjblslXvO3gSHw+aCT64s2fDXPDvaMPyKeDUOwUAvVcJ7bw2q6c8bPTm0APuSPmPu7VWbbN93Xgf49+uI+Ut89Dzdlf7YpqY/rOusUM/MHuCm09q+z7+9RCm2zPeJ3kf0n/jltvW8Fw3nj9VMA8KFsilvlwxv14f22BbfFrc1H5ZMAKyfY1OSUJnEnCKIGOHmr7yIijMeExBRWHF44QYy9BYhnXxBs1jVzd6TbjuiV6r1Oor+0BztH2DIXZalhua0kvEMMA/s1Uh5midCciXoln500z161RWv3yQog1LYw4T4N87v4AxdLhQOsu4fPVW5fF+p90roBjg8LgdDNdHcuqQDxUxLiHGTY+PHj+HI5pdunozIUWdkpfLG/hU+v0Hj7D34IlE1UmhajpVeP7idXAqc/3mfUjOn4+L0dQsl5KQvalRWHI6M1GDkUJCwA4Bpwky3ki5UJ9t0UtGYcUnKCnOGGfPmJ95WUbPl1bEmN5fCYWAEBACiSVA4cLfyC1SKA+4X59pPQFZMyvveUKnLbkW7avvVoGeLf5Kx8If1ljdzsa0LR7PXrBcLWNo0Ly3MRw/7Qfs2H0E5Wq+g7I1OqiHXihWmN+erddE0+lzV/DKi9Xx7U9/qs2u7eW3lsanvk2nDI+dPA9uOL1zz1G1qN9aGT2OGzy3eGsQXm3TXxOEx2E5Np7zt3mZ/mrb/jhy7JxeFFxCwqUkplO3POb2OjeCQoz55MDVCaSd/jlNkHHIFGWccmDIcwotTl9ysS5DLtRnHI1CjQKMaRRjjGMZls2oa0g4fjEhIAQyHgFOnRUqkFvz+NxVW9yYEgi5ew/3HjwEvWWm8faOuSB+5OffYPvuw+jX4w3Qy8anACfN/DlO/Zb1dGj7EvhzcabW7d3mqFyhJDaumKrWWs2d2hf+WTJZFjWe07v0x7pdGPTZfHCJxJB+b6s9Bzn1yr0IjRkdOLCcsnypfjVwWpU/mVa8SH67NRTMlxPctPrnr4djw/Kp+GPx52Zj4znjmf7NrAHgE+aWFeq/q6tP3+qhs5ZUWLYn5xmXgFMFGTFSUNFTxicoeU6hRfFFMUZRRvFFoxCjIGMa89FYhoIuo64hIQMxISAEMiaBlxtWA70+879dBQoqUuB2CjPn/YbA7P6oWqkUo+KYaQSFEPcJ7NB1DNZu2q2eIuZyBNq4YZ2xeNlGMI15mNe0rH5McaivsdJDrmPj+ir9PMA/Cwxu1p9AD7lzD2MmL0K/obPR+Z2m6KAJvKyaeBsz5APVxP/aD4a1p7xVoo0XrkPjVCGnDrlBtiNPjTIPpza5hc/+f08iPtt74AQoWlnORjfiRD96FK7W6MVJkAghkAgCThdk7ANFmS6uuC6EcbbMNC/L2Mon8UJACAiB9EygRtWy+GzQe5j37UpUrd8JdV/9CDVf6gb+GggXl8fnIdtz4Dgav/4JWmiCx9vbE0u/GQXWqTOrW6sCVvwwFkzjtFvTNwaAZfR0PeQvi+hrtvRfJOH+e+9/9DkoivR8liG3xuCToXxKdI3mHZs5oRe4jyIfJGJe9p/7O7ZpUR8DRn6J2q98qI31d8S3Hqt7v6koX6sjnn+lBzhl2PHDcVjxxzZERUazWptGD53pVKejxyxnWikZ8UnPN94faZzCZT84dVv/tV44f+Ea5D8h4AwCySLI9I5RbHVs3wb0evXr1RU8plF4MWQc03jOvHo5CYXAEwJyJAQyBgGDwYBmjWupX5j4cnJfDPq4PRZ/PRy//zQOpUsUihcCp+9aNquria4x+GbWQDVFaFkof95Albb8+9F47ZXaYBk9j7u7G/LmyaHWWuniZaI2xXnu4jXwIYOWTevAz89Hzx4n5JYu9Z6vCAox/gpI3VoV4zwk5OPthY+7t8bfq2eg+3stlGB0d3ePUxcj6I1btXg8tqz6Agf//tr45CefQB3c9224e9j/+Pq0ZzusXzYlwcZybN9d6xe3FmrzvwaoVa0cOrZrrJ5I//Sjdhgz+ANtCnQKOM6ihfMxu5gQSDIB++/oJFcfWwHFFqch6S2jUYAxZFxsDnkVAkJACAgBEqD4qflcOTSqXxVlyxSB7mFimj0L8M+MD95+FcWK5I8jhEzLGQwGlYd5WUZPo6D6bs6gOAKGP6s2pF8HNH6xOiio9PyWocFgwP9erQOurYqvz2y3fZtGKKeNz7Ie03NOk7Jf9+4/jLOR9P37jzBhZFclYvXjN1o1MC0ObvXRd8gso2ergcmDCpbHzMf8egVsm1sLvffWK+pa8HroxinU75esQ3hYhJ5dwvRAIJXHkCKCLJXHKM0LASEgBNIMAe4W/+wLH5g98ZeSnacooTjhpqgp2a6ttmw97chpQ0vjrv2m9fj4eIHeNNMHFKwdN9e8hUHBdxCj/W9a3tYx16b9vmY7+HQs8/BhgLVLJ6KG5knjuZgQSAwBEWSJoSZlhIAQEAKpSGDM0E5YOCthm0kDcKjHFCUUJ/fuPbSZnwKEG6QytJnJyQl8slJ/wtEy3L3hS1StVDpOi9HR0Th5+lK8C/ovXnZ8jzY+Jbpl+0Fws91N2w6oNukRzJHdH/SqqQh5EQKJICCCLBHQpIgQEAJCwJUIcP8setXK1uig9glzNGQZlk3oWChAOJXIkGXpKXqn29gEta33kXulsY7ksLDwCPWbn/O/+x3b/jls0zhNzPViXDdmrx/Xb9xSDyRwLd6A3m9h3NTv8eeGf2DriVV7dUmaELAkIILMkoicp10C0nMhkF4IxAAhd0LjrJvitg+mRsHBIdNTxSmzTSunISHGMizLOiyNIsu0LWvHoY9/n9LXxxtTx/ZIUNubHvfVct2XZT+ccf5S/WoY0b+jXeN6MVseLj5BOmfBCrzS+lN4enhg/PAuePP1hmqPt35D56BTr4k4cOikbIHhjIuVgesQQZaBL74MXQgIAdckwH3I+CFvuUbK8nyH5vXhCOip4pQZn0xMiLEMy7IOS6MAsWzP8nzslEWqmMFgABfqJ6RtPS/3PVOVxPMyedZimx64qvU7q937bVVhr6zuqWPI9XumdXDx/uDR81GnyUdYtupvjB7yAeZO6wf+NqbBYEC7Vg2x/IfRyJTJB+27jEb9Zr1w+uxl0yrkOJ0SSI5huSVHpVKnEBACQkAIJI4An1K0XCNl65x5E9eK7VIUSFyfZqtN03iuZbNdk3NSEuJ9e8PiKcuElKXHznJRvrubG/r3ehPb1szEmiUT8HKDanB3M//YLFIoL6aO6YE9G+epbUpkGwznXPeMWIv5OysjEpAxCwEhIASEgAUB1zk1GBz3vlFMmvbcYHC8LD121qYsM2fyVd4/03qtHbMsN781GAzWkiVOCMRLQARZvIgkgxAQAkJACAgBISAEkpeACLLk5Su1uygB6ZYQEAJCQAgIAVciIILMla6G9EUICAEhIASEgBBITwQcHosIModRSUYhIASEgBAQAkJACCQPARFkycNVahUCQkAIZAwCMkohIAScQkAEmVMwSiVCQAgIASEgBISAEEg8Abcd+y5ATBjIe8Dme0D+PjLYPWLn/gug7TpwEbR/Dl7Cbs32/HsZ+45cwb/HriX+jislhYAQEAI2CLjVqFwIYsJA3gPyHpD3QOx7oHqlQqA9V7EgaNUqFEBVzaqUz4/KZfOhfOk8Nm6nEi0EhIAQSDwBNyS+rJQUAkJACAgBISAEhIAQcAIBNyfUIVUIASEgBISAEIiXgGQQAkLANgERZLbZSIoQEAJCQAgIASEgBFKEgAiyFMEsjWQMAjJKISAEhIAQEAKJIyCCLHHcpJQQEAJCQAgIASEgBJxGIEGCzGmtSkVCQAgIASEgBISAEBACRgIiyIwo5EAICAEhIARchIB0QwhkOAIiyDLcJZcBCwEhIASEgBAQAq5GQASZq10R6U/GICCjFAJCQAgIASFgQkAEmQkMORQCQkAICAEhIASEQGoQSBLytDEAABAASURBVC5BlhpjkTaFgBAQAkJACAgBIZAmCYggS5OXTTotBISAEBACsQTkVQikDwIiyNLHdZRRCAEhIASEgBAQAmmYgAiyNHzxpOsZg4CMUggIASEgBNI/ARFk6f8aywiFgBBIRwSu37yNDVv24c7d+6k+qrDwCDx4+Ej1498jp0FTJwl84Vi2bD/oEmNKYNcluxBwGgEXEGROG4tUJASEgBBIswQobm4GhcCahYY+MI7rv+Pn0G/YbFy6ctMYpx/s2H0EDZr3dsiYVy+XmJD9bNL6U/y4ZL0q/tPS9aCpE+0lJiYGIXfuGQWbFmXzH8cy4vOFccYUFR2NW7fvWmXC9k2NbbFNm41oCXp9uojUouSfEHAZAiLIXOZSSEeEgBDIyAR2/HMY9Zr2tGpjpyxyCE1YWLgmXu6gXcuG+PSjdnataOF8duu8fDUIbHfYuAUwtaUrN9stpyc+fBSGXgOmGwWbHp+Q8Natu2jdcbhVJpasxkyOn9Gtx/XpIjIhfWFeCrl3uo1F2Rod4jXmY36WExMCjhBIE4KM3xy//n41Js9aDNNvivYGeOzkBXUT+XvHv3GyMY43GOaJk5iCEZGRUQi+dUd9g+S4OD6Ok+NNwW5IU0JACLgIgby5c2DTymk4suMbMxsztJPDPfT0dEf1qmXRqH5Vu5Y7Zza7ddLjtOKP7bh9O9RuvpRI/LhbazMelnx4/vmILjAYDCnRHcWV18meTR3bA74+3inSH2kkfRBIkiCj+ue3gLIOfFtgnobNP9a+vYUkmFxUVBS2bDuI1Wt34pH2DdCRCq5dD8aS5Ztw4tTFONkZxzTmsUykC5z95Lg4Pst0Z54f1/rWqGVf9Q2S4+L4OE6OV2/nq+9WxftNjGx127R1v15UwoxHQEYsBJxKwM/PG507NsOI/h2N1rJp3SS3MXDkXLP7WuuOw9T0ZpIrTqEKfL29kDMwwK4F+GdOMYGYQsOWZpKZQJIEmbeXJ7q/3wJTRn9otJ5dWsHdzU0Zj03Thn36DrJk8TMO6effNthc69B3yCw8fBhmzBvfAfOyjL5+YsDIearI7AXLjW0wnflUQgq8jJ/2g7FtvV96yDRHuvDC85UU2/feaqKyN2lUQ52T67hhnVHkqbyKKW+Y08f3RKXyJVU+eRECQiD9Enj0KBxdek9U9xfeR01HGhYWgS8XrFAzBJwJsGWcKTAtl5LHA3q/pTyBuodp7tS+8M+SyWYX/tzwT7zjSe0ZD5udlwQh4CCBJAkyd3d3VK1cWrlv6R5/rsrT4EJRLpyMjonB1p3/onKFksb052uUh4/2zULvW748gahdvbyZPVuhlDaNdxdBwXcQo/2v51WhnRc3dzc8Xbqwsa5yZYqo3EU1waK3wXTmUwkp8FK8aH7Vn+pVyoI3yeBbd8HxsT9Mc6QLXOdBtpUrlFDZSxUvaOTZoG5lBGb3R2Y/X9StVRH161SGf9ZMKp+8CAEhkH4J8N77TrvGao1Y1UqljQPNkzsHWjari2zZshjjuDaNZoxIwEFMdIzmuQpVMxucPeAC+9shoeBTnpu3HcC9Bw8TUNuTrPxibuphCvDPAoNbykw3shdPFczNQEwIuBSBJAkyjoTroM5fvI6Z839D/Wa9sGf/MQzq0155cQ4ePo2XtCm5cVO/x6kzl8G8LKMbBRo9O6b2UaeWSlRERESC3+DWbtiN9Zv3IejWHb2Y1ZDeunfffMXoVn/xhSoqX8N6VYxxTGc+laC90ItGj5XlN0wtySn/6Nrn2Ab1eQvFi+RX4qlfj7aqP0xzSiNSiRAQAumWANeTUgidPHMJf23cg9B7sQLIdJ0Yv7TpAEqXKKTuL7zv6FalYinQ9HM95P1XL2crvHf/IfoP/xJt3x+hrOeA6aAnavrcpZih3fNDTZ7+tFWHtXiWO3T0DLiFh7V0y7iX6leLMy59HHrIsVuWs3X+QJt9IVd7xjV08T21aat+iRcCiSGQJEG2dechVKzzHl5p/QlmfbUMVbRvassWjUa7Vg1BQbTs+9F4qX5VfP/LX3jtzYGo8Py7+OOvnXb7yRsPvWMHDp/Cx4NmovegGeg/4kucPX/VbjnTRK7HWrdpr4patXaHemxanSTgZbcmLKvW72y2zkFfp6WHXGvGP+gEVJvgrBSlnHL4/pd1qqyp6370pEU4dfayEqsTpv+knojik1Eqo7wIgXRGYNuO3Zrn/FY6G5X5cK5eD0a9pj2N953Kdd9X5606DMXCH/5Q3irzErFn/Lu39kQk7x17DhwHjceWxjIsG1tL3Fd6suZM6Yv1y6Yo+27OINSoWha/aff5XxaMAB9CiFvKPEZfNmI6ruqNuqLdByOVp808d8qcDRg5V3Flnxo0/1gdv95xmBKdbR+Lz88mfgtODVvr0Srtc4xf5u1Z+y6jE/XZY609icsYBJIkyKpUKoXZkz4Ghde+zfPx5ZQ+KKZ5gnR0RQrlBZ8O2r/5Kyz/fgxmTfwY9WpX0pPjhPw2su2fw6A7fuaEXsY1Bn/88jkqlCsWJ7+1CNZB8bJdq6fas2Vw5twVfP7Fj1bXo40d+oG6ybRpUd9YFadUX2lUHa1eqxevMR/zGwvbOKBn8MGjMNwNva/+QPWF+lzIausPXq/qyrUgNfV75vwV5MmdHcG376rzrdp08M49R+Dt7Ykc2bNi78Hj+Gfvf7j/IHaTRr28hELAOoG0Fbvgu59B6z9kTLoVZTWqlTPe8zatnKaOt62ZicPbF+Lg31/j+3lDUDB/rgRfONZLS3DBJBbgbATXGI8Z/IGaWh3Y+y0snDlAjWvn2tk4tG0h3mjZwKFW+AS6/kXYVujIg1icJl23bLLZE5tfjOuhhCUFpi48GU4c1Q2+vt5m/dPHNGFEVzUma1uLjBrwHn6YOwTTxvaAv39ms/JyIgTsEUi0IDtx+hLeeG8Eho9fgC4fT1JeMlvfFl5q1RedP56IkRMW4tU3+qt1ZtY6dfrsFaxZtwuVy5cAxRT/eGiBOfzh5elprYhZHF3M/FYzeebPeE4TY5M+6463276MlWu2o0X7wVi3aQ84BWBWyOKE3wj5iLXuBrcXMh/zW1QR55Qev0uXbyixdOVaMEoWL6jEXoM6z8b7FA7FIm8Ojhi/tZYsViBO+xIhBNIyAXrGaPoY0qso44c973f8kufp6QHe9wK0D3SDIf61VfnzBoIL5e3dr6ylsQzL6mydGfKLddXKpY1rXhtpsyU85xgduW+yL9m1L5uLFwxXIk4XqbbCqZoASu5tJqyNieMytZrPlUPuXNmRPVtWuLsl+iOWwxfLYAQS/W7J5OejRBMXqCfUsgVkiYP5wcNHGD/tB80lfw9vtX4Rfr4+cfLYizh74SqavjEAP/26QZsmrYbJoz9Edq2dj7u3xoSRXcGFqPO+/d2qp4z1UqhxDzBLl74j5/FtlHj0+Hn1kyAGgwGrNVd3zWplwZsjHyenh4vtWxp58BtfWQe3FDHNx0fKLeuTcyGQFgkEBd9CrRpVlZn2f+LUOaan6eqY04jcUJUbqyZ0YFwPa+uLsWU888ZX/4MHYcYnNvsMnomXW/VDjUbdQC9/fGX1dP1elpAyell3NzdQ2FDExWeOile9bgmFgKsRSLQg47cqfrv6tOcb+PD9Fg4Z81KIWC6+5JTexOk/g9OMfEKIT0NyfZYuMriWi2u67MHj9Ojk0d2x4ocxmPRZN+hPG7q7ueGVF6uDrn+6y/lHq3uo8uTOYaySe39xDzDuT5ZQ27v/uLEeywPejFhf+bLF1Nq6DX/vw5Fj5yyzxTnnN7E6tSooT5rl9GnZ0oVV/praFIdlGs+f1aaSVQZ5EQJpmACnKGkUZR3btzETZTWrV0nDI0ta17nsY+/GedDvA6a18YnLTz9qZ3M6jWldO76mvPX3Hj8gYFre9Jj3ymaNaxqf2CzyVD5wVuCLcR+hRdM6plmTfMyxcBaAYZIrS/kKpEUh4BQCiRZkeuv8CYp6TXuqRZHxhcyrl9NDPsUzdMxX4Le16lWeRt8P2yJLJj9wfRbFBa15k+dhzaum16GHvBnlCsyGKbN/ibNnzaiJ32Kc5oGjx2vd5r2qiOmCfHrkFs4aYLa2gLs/O2JjhnZS9Vm+xMTE4MelG9SC2uZNaqN18xfg6+Ot+nfn7n3L7GbnnL7gU6EUsJb2Uv1qKu+brzdUnjbLdHmCU+GRlzRMgEKM05THT5xWa8dMRRk9Zs2aNErDo0u+rhctnM9sirCRNk1oadwih1vlxNcL/Uu3fn/58IMWqm5OO3L2Ib7ySUnnfpHcN9LSq+fIOT9LLNu2V9+AkfPAhym4qN9a/Xp9nHkoKzMWlmjl3IkEkizI3mjVIN75/bFWBAvFyq49R8Gnh5b/sQ21tHl3TjNmyeyrNjrlNzH9RqBvG+HIuPmEJXe8p1cqPjtxKu4u/nziiFMG8U1DxtcX7sW2aPFfmDp7sVrP9sqLNcC9x95v30Qtvn+762hctvLjwJb1cq1ei7cGwfRGwaeWmI83EtN43sB442GamBBwGoEUrkgXY3qzlqKM3jI9Lb2G4RER4NpTfmm0ZVwzy/toWmHA2QJbY9HjQx9vo+Hl5QGun6VHL6HGL+aWTOzVx88ZbrTNhw6staXXxxmhTY8ftkhIyHKW/ZFzIWCNQJIF2d4DJ9R+NNyTxpZxUb1l4/xGMuLzheqbSZ8P26gnMPVpRsu8CTnnOgPTp2jW/jrJ+GRSr66vqyeWdK/Xe5o4sqybN7klKzbD3jSkZRlr5xERkTh5+pJqe9Sg90ChyXwd3ngZg/u+rTZv5DdQxtkz1nPh8g21OFRfq8fd+uk55Ddfxj2byM107bUraUIgNQhYijG9DxRlNP08vYfcw7Hx65/YnXlI7DozZ7Hz8fZSMxlcAuJInXMWrLA7Hs6w8Msw6+KSDXrieI9LqBXVvISsw9ScUR8fRODnS0KN5Uz7IsdCwBaBJAsyepnoibpyNchWG8iXN1CthTL9w+Uu/ZM+6461SyeCU3MeHu42yyc24fqNWxgw8ktc00L+kO4XXy7Br79vAb1XJnUmyyFvVgN6v4lfv/0MHKveiMFgUI96v93mJUA7hoP/ValYyur0JL/dcbNZ7tjvYFWSTQi4JAFbYoyd5TQljcfp3bgEQv/SaC/kEgsutUgoDwoE/ozdC8/b3oLIkTpZD2cy9A1m27ZsAJplWfaRfbU3Fj2NY7csL+dCIKMQSLIg00E1fblmvAv7n3m6KExd7GVKPgU+HqzX4YyQDwicOnMZYyYvQqOWfcFvmiMHvIufvh6OapXLYOiYr9H6nWHgBqv6rtfW2r109Sb4KwH2jJu2corUWnnGcQ8bHx8vHibZHoaFG3++RHfv6yF/zoQPJSS5EalACKQSgfjEWEaYpkwp9D6aZ4siyponKSl94INLtKTUkf7LygiFgG0CThNkA0x2Pqbr2ZqlhIt98bKN6lcB+OsA9WpVxLLvR6NZ41rIFRiAmRN7g9P+BccfAAAQAElEQVSHN27eVr8C8Mb7IxBs4yeZOBXLXwmwZyPGL0To4zUPthHbTuFTTK2a1VX7ktnOFZtCYVjPxsMT/3t7CG4EhcRmlFchkMYIiBhLYxdMuisEhECyEEiyIHNkUf+mxwshE7txH5845I7PdLPTTW6PRIsmz+O37z4Dfzlg2riPwO0w9Pz8Zvi/V+tgy+rp2Kj1acbnvZAju7+erEI+dr134zyHnrZct2wyuJ5AFUzEC9eQccEnv61yXBwfx8nx6tXxx8Q5rasztBcmlq/eloRCIKkEElpexFhCiUl+ISAE0iuBJAsyrg+gKHHE6BEyGOLfddoStr4gk8KFosoy3fSc04Rcq2YqakzTeWwwGJTHrHChPDx1CeO4OD4uZOV49U5xbR1FY3Ly1duSUAikJAERYylJW9oSAkLA1QkkWZC5+gCd2z+pTQgIAWcQEDHmDIpShxAQAumJgAiy9HQ1ZSxCIA0QWLFqLbjpq7Wu8klKWcBvjYzEZTgCMuAMR0AEWYa75DJgIeCaBESMueZ1kV4JASGQMgREkKUMZ2lFCAgBcwJmZyLGzHDIiRAQAhmQgAiyDHjRZchCwJUIiBhzpashfRECQiC1CIggSy7yUq8QEAJWCTRr0gjzZ000mqwZs4pJIoWAEMhgBESQZbALLsMVAkJACAiB9EVARpM+CIggSx/XUUYhBISAEBACQkAIpGECIsjS8MWTrguBjEFARikEhIAQSP8ERJCl/2ssIxQCQkAICAEhIARcnIAIMhe4QNIFISAEhIAQEAJCIGMTEEGWsa+/jF4ICAEhIAQyDgEZqQsTEEHmwhdHuiYEhIAQEAJCQAhkDAIiyDLGdZZRCoGMQUBGKQSEgBBIowREkKXRCyfdFgJCQAgIASEgBNIPARFkaetaSm+FgBAQAkJACAiBdEhABFk6vKgyJCEgBISAEBACSSMgpVOagAiylCYu7QkBISAEhIAQEAJCwIKACDILIHIqBIRAxiAgoxQCQkAIuBIBEWSudDWkL0JACAgBBwicOXcFu/cdQ1RUlAO542b598jpJJW3rPH6zdvYsGUf7ty9b5nk0Hlql3eok5JJCCQzARFkyQw49aqXloWAEEivBDb+vR8z5/+GsPAIq0MMDX2AybMW4+8d/1pN/2npervlLQtFRkYh+NYdhNy5h5iYGMtk/Hf8HPoNm41LV27GSXMkIrXLO9JHySMEkpuACLLkJiz1CwEhIAQcIPDVd6tQtkYHqzZw5FwHaniS5VFYOFav3YkTpy4+iUzEEcXXij+24bmGXVCnyUeo9XJ3vNXpM1y/cSve2h48fIR3uo21Oh6Oc9PW/Xbr2LH7CBo0723Xfv5tg906JDGFCEgzTiEggswpGKUSISAEhEDSCeQKDMCv347CppXTjNaoftWkV5zIGiiKBo/+Cu+0exl7NszFn0snwt3DTXnDQu89dKjWLh2bGcfCcXF8HGd8hYsWzodPP2pntPx5A+Hr441eXV43xlWtVDq+aiRdCKQZAiLI0sylko4KASGQSgRSrFl3d3dkz5YVOTVhppuvt1eC2794+QZuBIXgzPmrVqcYHamQ06Hf/bwWDes+i67vNoevrzcK5MuJIf064NSZy9i646Aj1cDP18dsPBwfxxlf4dw5s4FiVLcCeXMiMLs/GtStbIynaIuvHkkXAmmFgFta6aj0UwgIASEgBOInwGnGbbsOwWAA/tn7HyjO4i8VN8fNmyE4evwc6tepDA8Pd2OGQgVyo0K54tix+yjkPyEgBJxHQASZ81im3Zqk50JACLg0gVV/7TRbSzV7wXKb/T3831n8sGQ9Bvd5G5zm+2rRanBRvs0CNhLuhN6Hu5sbChfKY5bD28sT2fwz4/LVm3j4MMwsLblOKDIjo6Jx7catFGszucYi9QoBWwREkNkiI/FCQAgIARchUKFcMeO6Ka6rqv98Zas9u3DpOj4dPgflyhRBk5eqo8+HbfDnhn8wcNQ83Lv/0GoZe5EGN4PmaTNYzRKlCaQYxH3i0mrmJEbeun1XeeuuXAvG+YvXk1ibFE9NAtK2bQIiyGyzkRQhIASEgEsQ4PopfS0Vw1LFC5r1KzwiEvO//R1N3xiAzJn98Nmg99TarWeeLoppY3pg+z+H0fj1T9TaL7OCdk483N1w/8EjUAxZyxYQkBn0lllLc3Ycp165x1nxovmxbNXWRO+/5ux+SX1CwJkERJA5k6bUJQSEQAYnkDrD9/L0UEKsZ5dW+Hb2QOTOld3YkeeqPI01SyZg7NBOsJx+NGaycpArZzbkCswGbiJrmnw7JBSHj51DiaIF4MjifNOyiTnm3mcLf1yDJo2qY0DvN7F2025s2GJ/y4zEtCNlhEBqE3BL7Q5I+0JACAgBIZB0Am3/Vx/vvvkKfKw8lZk5ky9qV3/GbHF+fC1mC8iCl+pXxco123H5apDKzrVcm7cdwLXrwahXu5KKS84Xrn2bMvsX9QsA7du8hCoVS6H5K7UxZOxXOHDoZHI2LXULgRQn4JbiLUqDaZqAdF4ICIHkI3BVEzqvdxxmtoCfC/oT0iI3XH32hQ9wRPNiJaSctbxvt31ZPRjQ7oORGDLmK3TvNwXcl6xzx9fwdKmnrBWJE8cHEEw3eOX4OM44GS0iuOZtqNbmb7//jT7d26h+GAwG9OzcCvVqVUSHbmPBBxa4Ca5FUTkVAmmSgAiyNHnZpNNCQAikNwIvPF8JU0Z/iIG93zJbwD9hRFe0bdnAqcMdoLUxdWwPcKNVexVnyeyLaeM+wuuvvYD9/54EN4OdM7mP5olrbHOxv14f15d1f78Fxgz+wGw8HB/HWaZUYT1rnDAqOhqLFv+FPzfuxvTxPfHiC1WMebgf2meD3genZ6OiolJsHZuxA3KQUgQyXDsiyDLcJZcBCwEh4IoEihbOZ9zwlAv3Ta182WJO7XKWLH4I8M8cr6hio5zu/PCDFvj9p3H4bs4gNfVpMFh/8pL5deP6sqqVS9scEzd+1fNahu5ubujQ9iVs/v0L1K1VwTJZTb1yerZTh6YOjSFOBRIhBFyQgJsL9km6JASEgBBI/wSSc4QxQMidUNwMCrFr3I0/ObuRlLrpCaMYTEodUlYIpCUCIsjS0tWSvgoBISAEHCDAdVWdek1EvaY97dqOfw47UJtkEQJCICUIpLggCwq+lRLjkjZSn4D0QAgIgWQiwPVmXJ/FdVqWTfDpxyM7voEjxryW5RNzzvVgXOvG37pMi+UT02cpIwScTSDFBBmF2IpVa9F/yBhlPHb2YKQ+ISAEhEBGIFC0cD5wfRbXacEF/uN6MP7mpX/WTInqTWqXT1SnpZALEUgfXUl2QWYqxHQRZi0ufeCUUQgBISAEhIAQEAJCIOEEkk2QOSK6HMmT8CFJCSEgBIRA+iIgoxECQiD9E3C6ILMnsgJzZEezJo3QsX0b8FjHa6+Mnie1Qu5MffrsZYydsgivtu2vNmzkYtm1G3aDC2f1fvFppa+/X42lKzfrUSkWchdt9u/YyQs22+Qmiwt/+AP/e3uIGsOgz+bj7IWrVvNbG/N7PcZj1dodZmPWC7Ndts9+6HESpi0CN2+HYclftt8/aWs00lshIASEQNoj4HRBtuC7n6FPTeo4KL4oxMaNGqgEWa0aVdG3VxerwmzLtl1Y9NNSvWiqhg8fhqldqZu1G4jlf2wDf9C3dvXyCLl7D70HzUCrDkNx5twV1UduULhl20Hs3X9cnafkC3/rbcmKzernTKy1e/3GLbTvMhqTZv6MfHlyoGK54li/ZS+avzkIO3YfMStibcw1q5VD0K07+GTYHFXm8H9nzcrwZ1TYPvthluDwiWRMbQKb91zHlr03QGGW2n2R9oWAEBACGZGA0wWZJcRmmkdMF2KmaRRppsKs8FMF8ULdmihfrgxyBgaaZk2V4wcPHynRtWb9Lnw+ogu2rZmJSZ91x4j+HbH46+FY++sk+Pn5YOrsJXj0KDxV+uhoo7//uQP8qZIf5g3FjM97qXH8uWQiuNnkV9+tAsfKuhhSaFqOedTA97D8+zFqzFmzZsL7PT/HoaNnWEQsnRDQxdjR03dSZUT0kvOBnwlTZ6dK+9KoEBACGYSACw8z2QXZ9p17cPzEaZsIwsLCNUHwEIUK5kdUVLTNfCmdsHLNdmz/5wjGDe2MJo1qwN3NHFX+vIFYMKM/Ph/ZBT4+Xna7x+lMbtBIDxKnA+1mdiAxMjIKwZrHigLKgezglGvp4oVQrEg+Y3Y+DfXFuI/An0Hx8/VR8Y6M+asvPkXJYgUwacbP2nV7pMrJS9omQK8YjaOgMGOY0sZ7BEUZQwqzlG5f2hMCQkAIpDYBc5XhhN6UKlHMrBbeZPmtlzdZ3mz1xMtXruGvDVuwftNWXL12Q492iTD03kMsW7UVL9Wvivp1KtnsUybNQ+bjbVuM3bl7H/2Gzkbluu+rzRlrvdwdjV//BLv3HzPWSaHWsPnHoKfKGKkdUGy9020sBo6cq53F/qMQ+3LhClSq+x7qNPkIVet3Rs/+XyAoOCQ2g43XYkXy48DhU9i9z3w6NVtAFvUTJCymj7lh3WfxwvO2x8zftuvUoRn2HzqJg4dtC23WKZY2CCxd92Tt2NEzd1Jl2rJUyWKgkRjvGbxf8FgswQSkgBAQAmmUgNMFma0pSt5kJ2jTEbzRfvvDEqtCrHixwmD5lxrWTVWcV67eVF6lurUqIrH7/FDgfDxoBrZsP4hxwzpj08pp+PXbUSjyVF68++E4/LVxT4LGyDVqYyYvwox5v6Lru83x12+TsPLHsaoOru0KC4tQx9ZeXn2phmq3W9/J6Nx7Evb/exIUd6Z59TFzLyEPD3fTpDjHJYrmR45sWWXaMg6ZtBdBz9jmPTfMOm4q0MwSkvGESxg6tm8joiwZGUvVQkAIuDYBpwuybTt2qxFTWFlbO0ZhpjKYvOhCrOZzVZTH5vSZcyapKX8YqU2dRkVHI3Om2Km8xPRg5Zptyis1b1o/NH25JnIGBqBUiUKYPr4nXqxXFXwik6LN0boP/XcWv/6+BR91bqUJsteQL08guDkk17U1rFcF9qZCc+fKrn4UuEenltijeefe6vwZ6K1b/ddOcJzsQ0LGzB8mLlQgN86dv8qiKWvSWoIJUHTR88WnKOf8chK0UV8exkfj9mDUl4fi1EeBFpt2WEs/rPKzLI11xSngpAgRZU4CKdUIASGQJgk4XZBt37UHE6fOAZ+2JBFbwoxpxYsWBtN1IXbw0FH8uvwPzTt1nslp1rhm7O8d/+L5GuVRtnRhs3HQ+0SBdvLMJZy/eM0szd7JwUOnwHVfjRs8B4PBYMzK+ugBMxiexBkTTQ4yZ/JFl47NsGvdHCz6crBa0E/P2tgp3yMqKsokZ/yH9MbdCglF5sx+8WeWHKlOIGc2b9UHrg+j2KJRoFFc0VSixQvjmYfG/EvXXcR/Z+5Cr8siu9NOdVHGkJXyC9wEzbPOYzEhIASEQEoSSOm2nC7IoIcfoQAAEABJREFUOADeROkpm2hDmCkh9sqLqFk91iOmCzGGLJ/aFpjDH9kDsiZ6jRQFDreP8PPxtjrlmStnNuXRim/tlykHTjF6enjA29vTNFodZ82SyWq8SrR4oYCrVL4E5k7ti55dWuE3zet27ORF2BszvW8UmJzqZHXcAuNG0G0l6ngu5voEni7qjyGdn0m0oGrZsKBWvlyKDJRijPcGvbHg4Nv6oYRCQAgIgXRLwOmCjDdTnZYtYcabrYenByjA6BFjqJdhmDlTJgapZrm06cW6tSvij3W7cPlqUIL7YYBBE2JuePAozKr36dbtuzAYDJoICoCj/3l4uCNam0alWZa5G3of9FpZxvOcQm7T1v04cOgkT41mMBjA/cUYcVMTV/bGzKdf16z/B8PHL1BPdy5dsRkUmxWfKc7iYmmEAL1biRFlQzqXQ6sXC6XYKPllznQvQ64tS7HGM1RDMlghIARciYDTBRlvnlw7pj8xxcFaCjMKMFtC7KUGdZXnjOVSywwGA9q2qI979x9i8Oj54NOSln2h14iCjU9RWqb7+nqjcoWS2LnnKI4eN59+pUD67fe/UTB/LhTIl1N5trJnz4oz568qr5neDoXgsVNPnn6roIkftrNp2wE9iwpZH/cZY39UhMXLw0fh+HLhSkyetRiWa9Zua9OOLO/t7aUEYlsbY6YY7PxOU7D9tzqPxg9L1uPN1o3ArT8smpNTFydAUfZF/yqoWyWXQz2lGKN3zaHMTsjEJ7H15Q6srl+vrsaF/jwXEwJCQAikVwJOF2S8odJLxhupLWFGQWYKlB4xCrH/vdYYuXPnRGov6mffihfNjwkju+K/E+fR8u0hWLxsI65cCwK3qaC3qcen09B3yCzlCfPy9GARM3ujZQPk1qYmew2cjm27DiE8IhI3gkLUTzCt27wX3d5tjgD/zMiS2U9N/XEz1nWb9qp8J05dxIARc3Hv3kNjneVKF8GrL9cEn7RcsnwTuE6N+5qNnbIIy1dvNeazPMiS2Rdvt30J+w6exICRX+LMuStqDFt3HsKwcV/j6VKFUa5MUVWsuDbm0YM/wL9HTqsxL1v1N7jLP8dMr17hgnlw4dJ19ZBCB61Og8GgyvElIiIKO3cfAX9SytRYF9NTw6RN2wRaNixkO/FxCkVbSouxCSbrxXgPMf1i97hbEggBISAE0iUBN2ePasXqteDWFpxysCXM9DYthRiFGj1np8+ae5X0/Ckd1qhaFssXjVaCacT4hXixRR/Ua9oTb3b6TJtuPYVBfdrjs0Hvgx4xy75lz5YV3ES1WOF86NRrIirVeQ8vaGXpzRo/vDMa1ntWFTEYDPigfRNw41aKN+Zr0X6wll4FLzeopvLwxUObsuzfsx1ea1xbE1IL1N5mfFJy267DGPbJO3Y3p21Uvyr693oTXAfW9I0Bagyde09UHq6pYz7URKEvm1BWt1YFLP1mFLh3GX/vsv5rvVV+jpkbzObNnQMHD58CN6ZVBR6/cN0cvXDc6d/Uflq6/nEOCVyJgCM78t+8FZZiXeYXORFjKYZbGhICQsC5BJxSm9MFGXvFKUoKMlvCzJYQoyC7d/8+q3AZ45YRk0d3x77N87Fp5TRl/BmlLauno12rhmqbDnaWu90vnDUAY4Z24qkyLpSfO7Ufdq6drcr9rZXZvnYWGjc0f1KSbSyaO1j9PBPb2L3hS3Tp2AwTR3Uzq4/Cb+TAd8F05mN9qxaPx+vN62HvxnmoV7uSatfyxd3NDW+1flHl2bLqC9WXnVqfvp09CGzbMn/hQnnw5ZQ+Vsf89YxPEZjdX3n79HJs98iOb2DNTHno+SVMfQI3bz+KtxNHU3CTWN4z9A6JZ0wnIaEQEAIZiUCyCDIdIG+y1oSZPjVJAUaPGENTIUbBptfhKqG3l6faS4z7iXGq0WB4Ml0XXx+5bxfL0Wvm7mYducFgAOtlPoo7e3Uynfns1WetPL1sOTQxxbLsk7U8pnHWxsz9xyg8n3k6dprTNL8cpx0C/525a9ZZTk92eb1EnKcwHfGkmVWUyBNOTVpbf5rI6qSYswlIfUJACCQ7AevqIAnN8qbKvcVMq7AUZhRgtoRYhWeeTvVF/aZ9l2MhkN4I3LwdhqOa94vj4iJ/LtynGKMo0xf8M57pNx3wpDFfUo3LG2rVqAqGSa1LygsBISAE0iIBpwsy3lApyMaNGqg2fTWFogszCjJLjxiFGD1nDE3LyLEQSAECGaoJXWRxbzEKMMuF+xRnXVqXAOP/s/CkZShQMlghIASEQAoScLog0/tuT5jpeTg1SQEmQkwnIqEQSBkCFGL29hajGKPnrM6zjm2PkTK9llaEgBAQAmmdgO3+J5sg05u0JsxEiOl0JBQCKU+AYkufkoyvdU5jxpdH0oWAEBACQiDpBJJdkOldNBVm4hHTqUgoBISAEEhfBGQ0QkAIJI5AigkyvXsUZvqxhEJACAgBISAEhIAQEAJAigsygS4E0jYB6b0QEAJCQAgIAWcTuCOCzNlIpT4hIASEQEIJ8Fc0ho1boH6Fw1rIX8EIDX0A/sYtfy7NNM+Meb/hyLFziIqONjZ77OQF9TNtzG+MNDlYunIzvv5+tfoJNpNoORQCQiC1CNwPiivIUqsv0q4QEAJCIKMSuHItCFt3/qts87YDWLJ8E1at3aHOGb//35OIiIxEyJ17WLJiM9Zu2G1Mm/ftSrTuOAzd+kxB6L2HCuG168EqH/OrCIuXvfuPY8u2g+BPnlkkyakQEAKpQCDs5jURZKnAXZoUAkJACJgRaNOiPtYvm6LslwUjwN+M7drxNXXO+O/mDAJ/mUMvNHboB8a0A1u+wvTxPbFr71HMnP8rYmJi9GyuHkr/hIAQUATCcO3KLRFkioW8CAEhIATSKAGDwYAXnq+EVq/Vw/Z/jigvWhodinRbCGRIAlGRt3AzSBb1Z8iLL4NOIQLSjBBIIQIGgwF5c2XHgwePEBkZlUKtSjNCQAg4g8DVa9dxBdkhT1k6g6bUIQSEgBBIRQKcprx64xb8/Hzg4eGeij2RpoWAEEgogf/+uw7kyJ8kQZbQNiW/EBACQkAIOJlAWHgEflm+CT//uh4v1a+KbAFZnNyCVCcEhEByEojSnNrZ8+cVQZackKVuISAEhEByEOjebyrK1uigrHLd9zFi/EJ0eONlvNe+SXI05wJ1SheEQHomkBV5c3qLIEvPl1jGJgSEQPok8N5bTTBl9IfK5k3th51/zUHfD9vCx9srfQ5YRiUE0jOBrHmRJ5Ms6k/Pl1jGloYISFeFQEIIVK5QAo206UlazefKIUtmX7Pi7u7uiIqKRlhYuFk8TzjFefvOPQQEZIa3lyejxISAEEhFAgEF80LTY+IhS8VrIE0LASEgBJKFQJGn8iJ7QBas3bg7zr5kx09ewD/7/kO1ymVA4ZYsHZBKhYAQcJhAsbzeKq+bek32F2lACAgBISAEUopAgXw58Xbbl7Bo8V8YPn4hzl+8jptBIVi3aQ96D5oBpr/coFpKdUfaEQJCwA6BnB6xiSLIYjnIqxAQAkIgXRForwmygR+/hd/XbMcrrT9BvaY90XPAdOTPG4hZEz+G6c7/6WrgMhghkEYJuIWFhUFMGMh7QN4D8h4wfw+E894YrsXRwsIRTgvXwvCIZL3d5wwMwLplk60+MVm2dGHs3TgP9WpXircP7m5uaNeqIXatm4Mtq77AppXTsHPtbHw7e5ASZfFWIBmEgBBIUQLiIUtR3NKYEEgyAalACCSIADeKzZHdHxR6WbL4JaisZBYCQiDlCIggSznW0pIQEAJCQAgIASEgBKwScD1BZrWbEikEhIAQEAJCQAgIgfRLQARZ+r22MjIhIASEgBCwQ0CShIArERBB5kpXQ/oiBISAEBACQkAIZEgCIsgy5GWXQWcMAjJKISAEhIAQSCsERJCllSsl/RQCQkAICAEhIATSLYE0LcjS7VWRgQkBISAEhIAQEAIZioAIsgx1uWWwQkAICAEhkAgCUkQIJDsBEWTJjlgaEAJCQAgIASEgBISAfQIiyOzzkVQhkDEIyCiFgBAQAkIgVQmIIEtV/NK4EBACQkAICAEhIASAjCLI5FoLASEgBISAEBACQsBlCYggc9lLIx0TAkJACAiBtEdAeiwEEkdABFniuEkpISAEhIAQEAJCQAg4jUCyCrILFy+DduduqOowj02NkabnPGacmBAQAq5LQHomBISAEBACzieQbIKM4urHX5aDdufOXWPPf/xlmRa3zHjOA2txjBcTAkJACAgBISAEhEBGIJBsgiztwpOeCwEhIASEgBAQAkIgZQk4XZBNnTkftMW//g7ExCj7dcUfKu7HxZpnLEYboGY8Zj6G0M5pPGYcTcsl/4SAEBACQkAIpF8CMjIhYELA6YKMdZ88dRZnz13AhUtXlPGcpp/roa041uEqFqOJyjPnrmLC9J/wv/ZD0bj1p+j+yTSs27wXYWERrtJNl+lHeHgEvv3pT3w28bs4RoZXrgUnS1/v3X+IoWMX4Icl67TvAVT4ydJMuq00KCQMyzZeSbfjk4EJASEgBFydgNMEGdeM0SIjo9SYSxQvgsQYC0doH+o3bgZBN8alhj18FIYR479Bq3eG4fc/d6Jk8QKoVa0c7ty5h0+GfYk3PhiFs+evpkbXnNrmnbv3sWnbAdwICklyvZFR0fh7xyGsWLMd2/45bGa79x/HgwePktyGtQqCb93Bdq29vQdOICIi0loWibNDYOv+YNAozOxkS2iS5BcCQkAICAEHCThFkFGI/fh4AX9U5JMPw17d30dCzLTP6zZuBc00LiWPHzwMU6Jr7aY9GD34fWxcMRnjhnXC4L7tsejLQfj9p7Hw8/XGjHm/4dGj8JTsmtPbunItCANHzcexExecVvfLDarhj8XjzWzx18NQvGh+p7VhWtFTBfPgt+9GYezQD+Dl5WmaJMcOENDF2LGzsU9EO1DEqVmCb93G0FETMW3mfKfWK5UJASEgBNIKAacIsrQy2IT0c/VfO7Fzz1GMGvguGjesBjc3c1T58uTA3Cl9MGbIB/Dx8TKrmtN2QcF3QM8TpzzNEi1OKPyCb9+F7lnUk0PvPYC1eD2dYXR0NG7dDlXGY8Ylh7Hu5GyHjMiKbbAta2NwJE+WzH42xRg585rw2lirn3F6HoY8zyhGrxiN4916IHmmlFm3PePyBYqyE6fOKmFmL6+kCQEhIATSIwFzlZHIEfr7Z8Ubr7+mzNvHO04tXKRvyxZ893Oc/Ixo+EJt0Hic0sb1SCv+2I6GdZ9FvVoVbTbv5+cDb+8n3hiKigEj56F6o+5o1LIfXmjWG6+9ORh7D54w1sEP+w96TsT871Zh2pdLUbtxD7zYoi9qvvyhNi26A5evBuGd7uNQ99VeKv6F13pj267DxvILf1gDlt+49QAat+6Phi36KKvbtBfWbtxtXD/134nzqs4t2/81luUBRckrbfqD9fCc667e7DRaefl6DZyByvU6GYX4IeQAABAASURBVNMogn5Zvhm1Gn+k2mBbPP7u57/iCEjWlRBjv9iPv3ceUozIivVzTEePnzerivzIUc/DPqxauxNDxnyt1o0xs+W49HPm669dE3LmNSHn738xX2d2/eZtvPfRBHUtmId5O3Qbh/MXr7PqdG/LNj6ZdqeHTBdnKTlwLm8oWbyIapLCjN4ydSIvQkAIKALykv4JOEeQZc2CQgXzK7OFjN+ALc3/cTnLMp7alFOunIHQzTI9uc+vXAtWa8Pq1CwPd3c3h5qjiPt0xFxs3XUInw16F2uXTsBPXw1F4UJ50Ln3JKzfss+snkWL/8IF7QN/6TcjQKv1XDmMmfK9JsbGo1Txglj181hVvljhfJg0c7HylukVHDp6BsPHLUTb/9XHH7+MV+WrVCylph03/L1fz+ZQ2Lp5PXzU6X9qnB3eeAmfj+iMurUqqLJLV27BuKk/4I2W9VV/2Kfmr9TC1DlL8OPSDSpPUl5uaEJo5Off4p12Lytec6f2gbd27YeNXaC8fqz78H9n8fGgWfDPmgnfzx2k8o3s/w6mz/01DlPmt7TJs36Bl6eH6v+yRZ8pkT1l9i/Ytfc/lZVeuQ/7TcPtkFCwfV63GZ/3VOe9B80ExZrKmE5fKL627g8yG90yE4FmlpCMJzmyZ8Nbb7SEiLL4IfM9uUG7n/ALYPy5rec4c+4Kdu87hqioKOsZEhD7KCwcf+/4F+xXfMU4ExB86w5uBoUg5M494xfI+MpZpoeFR+Dr71dj6crNlkkIDX2AybMWqz7FSXQwgmNJKmMHm5JsQsBIwM14lISDC4935GcY9ijMoZqqVC4Pb++43jQWTu1F/bxJRWnTgZn8fNkdh4yemH+PnMbsib3xyovVEZjDHyWLFcDkz7qhQZ3K+ObHP3Hv/kNjXdmzZcXAPm+hyFN5lb3fvol2c4L2gVQAH3drjby5c6jyHds1Vl6zi5duQP8vPCISn/Zsi46akMmdM5sqz6nVKpVKx2lHL2MrLFemCJ6rUgaemmip9EwJJVjYJy7wX/D9GiXGenzQQvWHfer7YRu8pomyn37dYPchgN//3KG8bZU1j5tu9OzRQ6j3JTo6Bu+3fwX/e/V5xYuisk/31rhw+QYuXLqufVhEg96sQgVygSKpTMmnVL4XX6ii1opFRUXrVdkMS5cshEEfv6X6z3o+1urPnTM7uPifhVb8sU2J3Qkju6BKxVKq/prVymL88E64duMW/vhrF7OlaaPooudr2cYrmP/bOWXjFhxH38mHMO7rJ95bfZAUaCpNy8N8LMOyNNal53NuCIgoiyV67fotLF62EZNm/KxExcOHYbEJj1//O34O/YbNxqUrNx/HxAa8/6zdsBu2zFSAbfx7P2bO/w1hmrCJLW3/lffDW7fv4sHDR3EyUgCNGL8Q7FecRC2Cgu37X/7CC017osLz76JOk49QTzuu9XJ3lKv5Dtp9MBJbNU85PfJadof+8R69ZdtB7N1/PE5+trda86CfOHUxThoj2A5nItZv2Qt+ubXGgGOxxpjlxYRAchFwiiBj5360sgM/462ZPTGm5+eCfpp+7soh1yVxWpFeLooG0756eLgrgXb67BWzKTAKoRyaKNPzUlhlC8iMqpooMJ0GzZUzQHmv7mrf+vS8FEYUX/o5w8yZfNH6tbrKs0cPH+OSYidPX9K+8d4C12XRu7du81611cfGrfuRSZuqvX0nFPyma6uNSuVLKG8bPW66de7YFPSA6WW49q582aL6qQpNxxty9x6OHDuHerUrKg+ZyvD4hV7EsqULPz6zHVjyJCeu/+M3YD5Fu1PzlJH9qTOX1fj0cZ45dxWB2f1xJh08RRsY4K0AbVVPUgZhq+YRO3Y2FEEhYcpUosUL05iHxvzLNDF37Fwo9LossjvtVBdlDFlp8K3bGWahP71HE6b/hIYtPsb0L5di9bqd6D1oBl78Xx/s2nOUOOzaH+t2YfwXPygbNeEbVXbYuAXqnPE//7YB4eGRduuwlXjr1l207jgcPy5ZbyuL1XgKuB6fTFPerEF92mP3hi9xZMc3yg5vX4iNK6ehdvXy6NZ3ivZlco3VOhgZpgnHrn0mo2yNDsqq1u+M3fuPYbn2hUqPYzhw5Fxmt2kUYm91+gyNNKYfffoF2r43AjUbdQO/mFGo2SwoCUIgBQi4pUAbZk08U7YU/Pz8zOJc7SSH9kGczT+L+vbkSN8iNU8Nv8X6+ngr8WRZhiIjBjGagHnyE1KWeRJyTkFBYWFZJjBHAHx9vTXPUtKnIeh9ogdr8bJN4JSpqVG0FMiXE54eHpZdMJ7nzxuovG1ch6cbPVCOTgGzohjNgxapTam4u8V9m/JJymz+mZkt0RYTA0RFRuG0Nn3DaVjTMc7QvAcRkZFxhGCiG0vlgqWLZEH/d0smWlA1fyEf+ncslSKjoBh7rmolY1vBt0KMx+n5gNNv3/28FhNGdsWW1dOxftkUbP1jBuo/XxnDxy8EPWf6+B89CtcE0jAlTr76bpWK/rRnO1WG5eZM6Qt+4eFTxzynTRzVTd0fVOYUejl7/hr2/XsCA3q9iYb1qsDP18fYssFgQK7AAHR99zW0bvECNm09YNUDxwL8Ijd70sdKyFHQ7ds8H5s0Mbdl1Rc4+PfXxvgxQzsxu1XjFOnHmsB193DDn0snqjJ7N81DxzdfweDRX2HH7iNWy0mkEEgpAnE/6RLZ8huvNwfNXnGKsTt3Q3Hu/AVNuLjbywou6KfZzZRMiTm16UauH/tTc/874m3S7itw1zxh9LhEaeLMslu3bofCoP2fI3tWy6REndM7Ra+cZeGg4BCzaVHL9IScu7u7gdOYk0Z1heX2FTxfnIxbWODxfwY3Azzc3cHpksdRxoDjv33nnvE8MQf6deOaud9/HGt1nJxCTUzdrlgmUPOUJUaUUYhRkKXUmHb+sw+r/9xgbK79Gy2Nx+n1gB4gChJuF0MzGAxqqD7eXujUoakSKsdOnldxfGH83Kl9lSh5o1UDRplZWFg4IiKicELzdOsJplOax21M5+l5nRX6+XkrEXZKmyGw9nfMduj9P37yghKL7trfO+NsWVDwHXw8aCYq130fzdoNxEut+qFS3fcwbur34Jdi03KzFyxHg+a90XfILJXG6Ul6wj/u3gb8Qsm85Pj+201QvcrT4LKTdOIl49DE0iABN2f0WV/Qz9Bb8xJZq1MXY3qaPVHm6eUJfUE/Q71MSoUGgwGttOk/rvni2ghri2f5h8unGrl/V7g2DVDpmeL4Z+8x8OlG035yGoLu8AL5cxpvAqbpiTnmt85/9sUuStfLh4VFaO777SheJD8K5s+FrJn9tKlFX5zRvD96Hoa8QV+/cZuHdo0PI9ADRW8Yx2qamU89cj1KdHS0abTTjwOyZganJflBZXkN/j16BvyASUqj9Gjyuu09cALnLl4zq4rXftmqrWrrErOENH5CUTbx42dQu1KgQyOhGKN3zaHMTsjEB3+++3GpsSbuY8gnMI0R6fQgSvMEU1AEaF5fgyFWjOlD5RIGeqPv3TdZv6VlCdC8+DkDA5Tg0fMy5N/rtl2HwDrXb94LeoYYbzqlueFv84eMmO6I2RJVtsoWLphH7d04++tlaPhabwwZ85VaiM91bj8uXY8en05DnSY91EM0/Xq0NVvSYFknxzN+2g+4ej0YG5ZPwY61s7Bnw1wsWTgS6zbtVdOipmWKPpVXTYc+Xbow3LQvmFxTli0gC/LnCYTpfxRlgdqX5ctXboJfqk3T5FgIpCQBpwgyLubXLczKon6+4f2zZkWhAvnNLFq7CQUFWxcHN24EgXb//oOU5GFsi083jh36AY6dvKh25F+6You6EfAb2sHDp/Hx4FnoP2Ie3LTpNC8vD7z+Wj3Q/d5v2Bzl+ubCez5JxDUhG/7er33LfdVp01+84Q4f/43aJoOeIu5XNnryIrVTPZ+UzJzJF5y+LFm8AH5ethHsL4Uh91UbPWmRcYz6gS7e/tq0RwkQ9ptTjm++/iL4NOX0eb+BbbAtLtbv8ekXoPcwWptS1OuwDLlWY532YWBpfFjAMq+tc3d3N7z5ekNcuHQDH34yDfv/PQmu/fr197/RZ/Bs9RCErbKOxjdvUhsB2odgv6FzQKHJ63bx8g3tg+NrTJm9BDx2tK60lK/5C3nj7S5FW0qLsakmG8PaFGPx9jztZeBUXsniBbW/1VNGAaWPYs+B47gbeh8FtC91ehy/gH25YAWGjVugFv7r8Qz5ZPIPS9ajd9fXcf/BI+19/IvapsZ0SrNrx9eY1WHjvohcD3b0+Dkl9BwtaDAY8FL9apg2tgduat6tO3fua1+kzqhf8DimecWu37iFnDkCsGBGfxQtnM9utWHhEeC96YXnKyF3ruzGvORWuUJJUFAZI7UDtjuif0e8q01JcsqT+TgGrk3Vko3/+BBA0K27CAjIbFcQGgvIgRBIJgJOEWTsm71F/V3efxtvtNamNK1Ym5ZNWdzM+JTl+k1bQUstQcYOPfdsGSxeMAzPlCkCCp4mbQaA+1R1/HC8uql82vMNDP+0A+hpyZ4tC+ZM7g1+K+vebxqqv9hNc6d/gtXrdmH04PdQX7uJsE5nGIXfG/+rj5ETvlV7nnEfs7+0b4jDP33H2A6/VXM7C36zZn+rNeyKj/pPR/s2L6Ki5s0z7Ue+vIF4SxM+dNlzry8KMKa/0bI+enb+HxYt/kvticb91bhvGadU+nzYGnxgATb+o3jiz0tZ2rETF2yUsB7Nhx9mTeylPlje+2gCGr/+qfqAGdKvfZxxWK/BfiwX9E8Z3V3zJvqo/d143bjn2dHj5zFxZBewffs1pM1ULtaPr+dBIWHxZXFa+slTZ5FRxZgOkdu/UPi812M8Nm3dr7zb/CWQ/iO+ROMXq6Nc6SJ6VpshvUD9hs5Gjapl8U67xujVpRVW/LEVn2hfFG/dTvwaVn6Zu3NXE1Pal9Gr129Zbb97v6koW6MDGjb/WAkny0y8J3Xu2AwUSbpRNFnms3XO+2zpkoXAhxPWPf7ySO/fyjXbsUHz+FWwuK9Z1kNvOz2KoyZ8AwpBptPj98uyTdqXseN4rXHteJfSsIyYEEguAk4TZMnVwdSulx/Y44d3xs61M9UeWGuXTsDGFVOw7reJaNPiBTNRkiO7P2ZO6IXNv09Vedf9NgmbV05FoxeqwmAwqKHw55bmTeuLkQM6qnP9hdtkrP55nHYTfVmPUiGf2ty+Zga4pk1FaC90v7/RsgG2rv5CtfOX1pe/V01Dk0bVje1o2dR+ZssWjfo/e+cBGEW1heF/CSSEGkLvvQmiIiAdXqgWEAUREAUUqYqAIM0AoSPSUaQrWFGkCSi9g4L0jgREekgghBYEefNfnHW2ZpNsNrvJ8XkyM/fec8u3efHfW85ofR2vyrF8K03IzZnS16Idk8kEzqzp/e7fsw3d1djeaNXI3A7HvnXVVAzu+wb4x1EVsvqhj2/PxpmwZ/o4eOW4OD5jFXxmOvMmjz4dAAAQAElEQVT1dP4h/XH+MMVVZ1q9SnnExt5TfWQ5a37WzyxD0/tn5F+4YG7Mnz5Afa4cI9tYtXAMKlcsQ5cUaVev34tzXBRtnhJlPE2pdyg1zYzpY+Y1n7aUxpkifgnoo4mqJq0HYOnKrUrAhPZ5w/y7zrJGcVOrWgVwloext17pMASFtWXCsAFvqvL161bCzEl9cUSb2WrXbbTTUDWs157F3LwDip7XXmmgZqYW/7RZm51+aFN09OBO2Lh8svYldigyZgpUS4icwaMxfE1s7N/QZ/WYRvtl/W+4GhUNriTwmcaYZjaVawkmkwk9tVk/zniNnfwNqjfqBobOmPPlCowO7YSWzf6nlXL8b3C2LJg48h0V4zBEWz6t9ew7ai/ax9O+RZ93WqFuzScdO0uOEPAAAbcJMm7opxn7zG+88THdN42fH+rVraksV64cenKyXv3902nLgFmVMUipyfRIYNnrFENFUBBw1iyNtqRpr4w70vQ+Zdf+0DiarWL7wdrsHfvD8s7a1ftN0WIsRz/606zzjOWS4n7jtn14892PwMMV7B/HwjGdOn0ep85cBGcx3dGuyWRSS8oco96GO+r11joYwsLYNy5PdnypiM0pTIoyY7mkuuc+MW7eHxbaB7xPqna8vV4uxVFM7V4/U50CXKN9qWv2fC0lrpz1nUtyFHSceeKXwsyaINLLV36qDH76dgzmTu2ntlXo6a5cuT2CMdHOXYhQgqeZtsTP5VAui1r7Z8mcAZyBovDxS2P5nxbOwjdvWgfZtL9FMPxTtnQRvPhcTfB0uCHZ4W36AH9QGJILT1vSln41CoxNaDI9+pscHJxFiUJ7hx24LLr061FafhhC+7bD9I97Y+uqT8AvuCbTI3+HjUuGCwSkSGIIWP6/JoE1Ffo3Sj+v+qZ+LkEkxNgF7h2iEKPxWSz1EiiYPxfOnL2ELr0nYPkvO/CHJsS4r63HgKl4onxxMPZb6qWTsJFz1ksXWjl48rJDaVCMUZTpG/6ZztpdmUljucQaQ11UrVJRBYdNbF2+7M9lQUaI56Z3R3bv3n2MC+sK/aQgx2symdSbO5oZxBv3S/HwzZwvV2L4x/Mx/9tfVNDY8xev4s22z+HzTwfYHAhgXUbjoYBpsxaBy5/Fi+ZDk8bVwRm8ngOngnvAjGWN9xSInMmiQNSNWyq4r+2dji9BN2770PP1K2f8jHVZ3zPMRzltadSRVajRAbWeexeOYqb5pUmjDgs1DKmM6s+Uh1G8Wrclz0LAkwTcIsisO8xvuLQihQqAVrxoYfWtt0hh7dlgqozhmflMs65Pnv8jkEn75psnV7A6TPBfasq9K14kH+ZN64dCBXJjyOh5aNkhTO0he/HZGhg/rCt4gCHljj5pRnb12qPlSoayoAArUzSzRUMUZzSmW8+kWRRMhQ9JPWQeWpk6c5E5mOvYfwO9Gq9c1nMWRZ4HeCZ8shAMntr7w09w5Nhp1W1uZudpx8Yt+qBtpxHmfVQq0+oH66CQY2Daps/WRLtWjdR2CB4+GDHoLU04Z0XrjmHgaU4rV5tHnlgeM+krPFn7LbXE+PLrH6KV5suwFewjI/ivXLPTbngbm8q0BM58cWnUkf04f7jTmUAeDKjfrDco7LTq5F8h4DUE3C7IuP+D1uaVZiiQP6+ytq1eBtPavfYK8ufLq4z3jtKY7jWEvKwjLbRp/7lTPwCX1bysa0nWHe7xmvZRD/OetN/WTkefd15Fxozpk6zNlF4xhRgFmaNxUowx5EXNJ7M7KiLpSUCgVPECWPzlSHOA13VLJtrc8/S3s6aXrtqKb39chxkT+2DziikYP6K72oc2fOBbqm4u0fkHpANPXMfe+9tuVVyl8EtjQoc2z2FAr9cslkxza18I507thw/7vIEK5UrY9dcTOUvXa+A0MHTN1zNDcWDbPGxZNU2NiWErGOC1V7eWGDx6LhZoM3i6n7MrA+TuPXBSnbq2d2W8sTux95xVEWde3ZpP4fcNs9RMWpyFpYAQcBMBtwsyN/VLqkkWAtJoaiBAsZVDW6p0ZaxcxnSlnJTxHgKnTl9A6ZKFwNeXmUy2+6K4B5anME+c+gs3b96223GTyaSWKXt3bwnu27IuxJnp5k3qxLncd+vWXfU6N27GL1e2KPzSWP4nh0ubzzeqhro1nlQn1xlrzLot62e+h3PYuC+waft+FT5j22+HLK4Hj55WoTZKlSho7SrPQsCrCVj+v8ONXc2YMYPalM/N+ca9YPX/V1NF4Tc2ZS/NmC/3QkAICAEh4BoBbuLnqcqvf1irItQbvRjmYbsmYBg6gieVg7JmMma7/Z6z2EUL58WsL5aDITke8n1lhlZUf349hK2/HlSzUX5+foZcx7cliubHoPfbQt93Zu8a1140zt5x+dKZxRjeIey4N5KTIALiZEMgSQUZhRhNb5VR943GdOMz75kmJgSEgBAQAgkjULfmkxgxqCPmf/MzKoV0AsM78BVCIU174slab6Jzr4/RoG4l9H23FVwVQAnrCdShAYbD4Js/mrcLVfvI2Bda3SbvgRvwew6Yii7tm6Jd68YuN7Nr7zG1R87Rxn6mc58YxZajSj+btwzsgzMbPfFLR+6SLgTcTiDJBJnbeyoVCgEhIAR8h0CS9ZShIqxPWRobM5lMeLb+M2qv1s7V0/Hp+N7o16ONEmlrl0zE3k1z0L/na3A11ISxbnv3mTNnwJB+7cF+2ctnKBnuY2O7fOXRmMGdVX9mTe6LbT9/gt0bZqrlUUehe6zrjGtT/8blk0FbOG8oGALD2p+hOdYumaDCijBshjMbNbiTtbs8C4EkIyCCLMnQSsVCQAgIAfcTYLDqkNoVVdy8uGqnWHr8sWLQQzzQ11XhE1fdej73mHF5kHXrafaubJfBsxlwmf0pWawAuGRqMpnsFXeYxpOeFFVxmb14aA4rlQwh4AUERJB5wYfgk12QTgsBISAEhIAQEAJuIyCCzG0opSIhIASEgBAQAkLA3QRSS30iyFLLJy3jFAJCQAgIASEgBLyWgAgyr/1opGNCQAikDgIySiEgBIQAIIJMfguEgBAQAkJACAgBIZDMBESQJfMHkBqalzEKASEgBISAEBACzgmIIHPOR3KFgBAQAkJACAgB3yDg070UQebTH590XggIASEgBISAEEgJBESQpYRPUcYgBIRA6iAgoxQCQiDFEhBBlmI/WhmYEBACQkAICAEh4CsERJD5yieVOvopoxQCQkAICAEhkCoJiCBLlR+7DFoICAEhIASEQGom4H1jTxMQEAAxYSC/A/I7IL8Dlr8D/vzb6K+l0QL84U/z167+6bzvL7n0SAgIAZ8nIDNkPv8RygCEgBAQArYEJEUICAHfIiCCzLc+L+mtEBACQkAICAEhkAIJiCBLgR9q6hiSjFIICAEhIASEQMohIIIs5XyWMhIhIASEgBAQAkLA3QQ8VJ8IMg+BlmaEgBAQAkJACAgBIeCIgAgyR2QkXQgIASGQOgjIKIWAEPACAiLIvOBDkC4IASEgBISAEBACqZuACLLU/fmnjtHLKIWAEBACQkAIeDkBEWRe/gFJ94SAEBACQkAICAHfIJCYXoogSww98RUCQkAIeIjA/fsPEHXtBni9G3sPW3YcwOWIa/FunT7rN+9B9I1b8fYVByEgBJKOgAiypGMrNQsBISAE4k3gwT//4Hr0TfBqdD7+x194pcMQ8BoTcxthYz/H0eNnjEXU/aXLUVi4ZAPGT/tOibY7d2JVuv6DPn2HTMe5CxF6UjyuUlQICIGkIiCCLKnISr1CQAgIgXgS4KxX9YbdUKNxd9R/sRf2HfrD5Ro4czZu6reo/1JvTJ2xCCvX7kSvQdPQ4OX38evuIy7XIwWFgBBIHgIiyJKHu7TqpQSkW0IguQj8EX4eA4fPQtuWDfDzD+NQuWJZfDhiNi5fiXKpS4uWb8KC71Zj3LCu2LxyKtYtmYitq6YhpFZFDNVm0zhzpld09+49tNRm28pVa4c5C1boyXIVAkIgGQmIIEtG+NK0EBACQkAn8Mv631AgX060b/McCubPhX7vtVZZH46cgyFj5mHGvGW4fdty+VEV0H7E3vsbG7fuQ+N6VZSZTCYtFUgf4I9O7Zrg9p27OHbyT5XGH0yfOakPNi6fjNYt6jFJTAgIAc8SsGlNBJkNEkkQAkJACHiWAAXVoaOnUbXSY8icKVA1HpwtCx4rXQR//nVJPTv78eDBA3CvWFDWTDCZHokxvXxAQDqkS5sWN2/d1ZMArUhQ1szImSMIGQLTQ/4RAkIg+Qm4XZAdP3EKcdmfZ88hLkt+NNIDISAEhIBnCHD/181bd1C8aH5zgyaTCaVLFES+PDnUbFnnDk2RIUOAOd94Q1FVSiu7/9Af6kCAMW/3vuO4EXMLBfLnNCfHxv6tZtw488Z9a+YMd95IXUJACMSLgNsF2bKVqzFu0nSnNv/rH+DMNm3dGa9BSGEhIASEgC8TuHs3FhFXryNTxoTPVrVv0xgxN2/jrXfHasuXexF+5gKmzVqM/mEz8GyDqihfpqgvI5K+C4EUT8DtgizFE7MzwMTEBLJTXbyTGE9o8/b9XhNXKLH9oT/jJDFeUrxheM5BWhICbiMQGBiAPLmC8edfly3q5KwZ8/z8/CzS7T1wJm3etP4oX7Yo+gyejiatB2Dpyq0I698BoX3eQNq0/9XBZUzOuDGvVrUK9qqTNCEgBDxMQARZAoFv3LoX9Zv1Vt9qYxzEBOK+EH7rdcW46dZeV7iUwbaGj/tCbexlbKFTp8/j4cOH5uKMJxT20ecejSvEMTNWkrEfeocc9Yc+NL2cfmUaTX+mP+MkMV6SnuboStFG8UYR56iMpAsBbycQ4J8OQUGZcP7iVXNXuS/s9NmL2P7bITzX8gN06fUxjP8/MRc03OTWRF3YgDexe/1MHN7xBdYsHo9mz9eyEGOG4nIrBISAFxFwLMi8qJPJ0ZUduw7j9S4jVWTshLa/Q/tDWrfJe3DFtv96yKYZCrm2nUcgdOQcZMwQiMpPlcG5ixFo1nYQvvjmZwtRZuOsJTCqN8dQr1kvxGV9Qj9Vm4I1N5f+HT3xS/QcMBV3tKUWlxy0QvShabcW/zKNZpHo4gNFG8UbRZyLLlLMDoGIa7H4Yc1ZOzmS5AkCnAGrXqU8ONOti7LwPy/it9+P4s3XnkO/Hm3Qvs2zCAjwd9odfjHhF5TV63fBkd27dx/jwrqCJzqdViaZQkAIeJSACDIHuGNj7+HipUg8ePCPgxKuJadP74+F88LUt1V+Y3Vk9etWsqlw2aptaoPut3OHonf3lnihUTVMHPkORoV2wuwFK3Ba+4Nt42RIyJAhvTryzj/mzix/3hy4GhmNh9r/DO4+ccsZRMZUirp2wyf6662d3LT7Mjb/fgURmjDz1j6m9H7Vr/O0JrjSoVufCfhs7lJ07T0B5coUxdvtXkDDkMqoWrkc/P3TOsXAGeOpMxdh7JSvHRo38nvblxing5JMeQp8KAAAEABJREFUIZBKCLhfkP23kpZKECbdMLk0WbFCSVAwGVspViSfeoyMci5CGGuI+0P4x9yZFcj73+krVbGP/OCSzubtB1RvN23fH+eMoSooP+wS0MXYkVPRdvOTOvFqZBT6h45Sh4GSui1vrZ9hLj79uDcKF8iD75dtRI1nymP04E7xCktRqngBLP5ypAoKy8Cw9mz04Le9FYH0SwikagLuF2QpFCffKxelzcJwGZF2I+a2SyONNRwv5zdTezbh04Wwtzek/GPFsOfASYuNvtyztXP3EfVNOm+e7KoPTHv4T+KUcK6c2RCYPkDVF9eP2Ht/41r0zbiKJXn+voOnsHrjLrzcpDZW/LIDB4+EJ3mbCWvAu70itFkxGntJYcarp42hcijKeKUw83T73tIev3xNGdtDCSruBcuRPau3dE36IQSEQBITcLsga/p8Q/Tt2dWudWzfGnVrVUfJEsXwfON6eKNNC7tWp2bVJB52/KuP0majWnYYat4PNmDYzPhXEk+PJo1roGzpwnihVT+888Ektam/RbvBmDZrEXp2ecW8B+Rq5HVEx9yyWzvFEwWk0XbtOWaxv4T70tL6pYHJZLJbh3VirLacG6mJ00tXotS+Mx5IaN9tNMpVa6eMr2Thhn9rPz4v1ZZh9XL6lWnMi4/tO3gS3T+YiEYhVTCwV1u1pNNr0DQwuGZ86pGywKK1Z80YjoRHJ8uyZelSxUFjR67+O1vGezEhIASEQGohkMYdAzXWwT+qjqxokUL45+FD3NNmWPLny4PChQo4NGOd3nDPiNZrl0ww7wX7ZFxPl7plPF7OI+b2rHe3lsicOYNNfYzYPWFEdyz/ZgyeqlAKFE3c2Lth2WQ0aVzdprx1wsIlG1CxTkeziOThgpdf/xD9h81Q+0umzFyENRt3I/zMRWtXp8/cbHwq/DwuXIrE0RNn1ZLK558OMLPhnrmgrJns1tEwpLJ6XcvG5ZPNV6bZLWwnkdHIZ8//Ce00AVi3xpPo/14bBAYGoM87rVChXHG81mk4mM9ydtwlyYoAZ8Y27b5ikWoUaBYZSfiQI3swOrz+qogyJ4z5/6nnG1YDr06KSZYQEAI+SsBtgiyuyPvMP3/hEvz90ynjPdPisuvRzvdJ+Sh3p93mEiRnmDirdTUyGhkzpEdTTYB16fAiqlQsgyPHzqgZLgZ93LBlr8O6XnyuJnatn2EWSjxQsGXVNLUcwr0lP307BmEDOqBE0fxIm9b5ZmG9EfbtJ215sEL54qhV9XH8uHwzuLFez4/rGhjgr17XQoGrG9Pi8qPAGjF+AarU74zpc5einybERoa+rcQYfSlePx7eTaUzv2rDrhg14Us1g8f81GwUXZz54inKz74/CdrwGYfQY8xuDJ9x0AYNBdqjvENa/iFVnr401mXj4KYEEWXOQXI5k1/eeOUXuCH92msz6EWcO9nJLVu6iC+fsrQzIkkSAimDgFsEGUXV/Dii7zN/xc/rcPKPcGW8Z1pcFu3jgownALmEV+7f5TxH1zkLVph/o+79fR8DtCVRzmhZW8PmfRA6eg4++3wZLkdEacuMZjebG8Y24itVbDIMCRQ6XHosXDC3IdXx7Z79J7Fs5Va81qI+3m7fBFt3HlCzbI493JPDWbAaVcqrE6ZbNVHZRmvfL43lr69fmjRgOvNHDOqIapXLgX7u6YHv1pIzW4Dq/Obfr2CTNhtGo0CjuKKpTKsfTGcZGssvWvsXjobfgF6XVXG3PeqijFdWyuXLcZOm81bMQEA/sJM7ZzZDqmu39AmpXRFZs2R0zUFKCQEh4BEClv9F80iTvttITMxtMFAjY/1YvKjXwZCqaQJio2Fpztl96xb1zLVQSE0f39tiZovfjPPmzo61iyeoGa4f5w/H8IFvoW7Np8x+CbnhWG7E3ELxoo9Objqr4+y5ywgdNVvFQ6tZrQKe0JYIX3+1IT4cORubtu135uqWvP/Vekot1cYlspjfRJtRZHm3NOzJSpKorceKZUVo58cTLKia1y+o+ZdPot5ZVksxVr1qJXNiZOQ1873cCAEhIARSKgG3C7LaNava3ajPDfzc8K+DdLWcXj45rhcvR6r9V+X+nd3iMtgLr/ZXp/kuX4mKs0sUVvqyXFzXuGayjI1xo/7cr1aqTf48tfnV92uN2fG6Z12lihdEPiehL7hM+evuI+jwzhhV96A+r4Pf0E0mE95u1wTPN6imYidNnfUjeBpVFXLwY/e+4+Z+s+80pjkoLsluJMDZrYSIstDO5dGiQSE39sR5Vdt27MKyFavNhbi3zPwgN0JACAiBFErA7YKsiJON+kFZs5gxulrO7ODhG+6zYBBW2qxJfbF+6URsWTkVB7bNQ82qj3u4N5bNcXP/42WLgUt4tLKlClsWiMcTfbkhv1TxAg69TCYTGOajlCbc5k8fhHx5cpjLUpgN/qAdaA3qVoJfGse/Uk8/VRqcNTQ7/3vDNOb9+yiXJCRAUTalfyXUqZTLpVYoxji75lJhNxRi2It5C74z19S3Z1fzRn9zotwIASEgBFIgAcf/9XRhsNzfwT+g3EMWlDULsgdnQ8zNW+AzTa/C3eX0epPyyn0WPP1Hq/5MefAdccHZsjgVHHp/Tpw6h5faDkI9F15ZZCxDH/rq9Ti68jUrlSuWUaEe2L+KT5S0KGodhkKf4XPlatzLZqy0wf8qgcuo9uIipU3rh1dfCkGZks5nUZo3qQN7p0yZxjxje9b3A4fNVCE1XBmDsQz9rOuSZ6B5feefFRlRtHlajBn3i4kY46cglnAC4ikEfItAogQZv8nyDyg35u8/eASRUdeweNkq8Hnz1p1mEu4uZ67YS28o5t7t1BzOXldkL48+9E3ssALTB2DS6Hex0cX9a8ZyrQ172RLbD3f6D+jVNkHjoZ87+5FS6jriQkT+iKhYjw2XX+z4t0RvUMSYTkKuQkAIpBYCiRJkqQWSvXGWKlEQzzWsqvZSWefz9BJPMXH2Kj5GH/pa18fnTJkCkTdPdvj5xf2RmUwmMFZRXPvW7OXHZy8b++Up4zF/e/2NK41+nuqjp9tJTHsR1+7G6X7Eg0FiOYuud0jEmE5CrkJACKQmAnH/1z010YjHWPmOSJ585H/waQmNCeRqk1wSXPDZIHDZ1NqH+93GhXU1R+63zvf0c4F8OTHkg/YJ7g/9OR6Oy9N9Ty3tHQ23jO/H5ckur5S0OYXpykyaO5gxmDQ3748ZPlD2jLkDqNQhBISAzxHwYkHmOyzTB/iDAs0dy40JGTXbdTa7lpA6E+PDWb7a1Z9IcJwj+nM8HFdi+iG+9glEXIvFEW32i7nc5M+N+xRjFGX6hn+mMz/ChZk0lkusMdRFjWqVwWti6xJ/ISAEhIAvEhBB5oufmvRZCCSCgC6yGFuMAsx64z7FWZeWJcH0o1YzaYloVlyFgPcSkJ4JAS8gIILMCz4E6YIQ8DQBCjFnscUoxjhzVvtp18JjeLr/0p4QEAJCIKUREEGW0j5RGY8QsCVgkUKxpS9JWmTYeeAypp1kSRICQkAICAE3E0iUIGv6XEPwRJRujMavW5PnG5q76u5y5orlRggIASEgBISAEBACKYBAogQZT0YZrbAhSj8Dxep8jGV4n9hyer3mq9wIASEgBISAEBACQsCHCSRKkPnwuKXrQkAICAEhIATiTUAchEBSERBBllRkpV4hIASEgBAQAkJACLhIQASZi6CkmBBIHQRklEJACAgBIZAcBESQJQd1aVMICAEhIASEgBAQAgYCqU6QGcYut0JACAgBISAEhIAQ8AoCIsi84mOQTggBISAEhEAKIyDDEQLxIiCCLF64pLAQEAJCQAgIASEgBNxPQASZ+5lKjUIgdRCQUQoBISAEhIDbCIggcxtKqUgICAEhIASEgBAQAgkjIILMMTfJEQJCQAgkK4Hbd+4i4up1Zbx3R2cuR1zD+s17EH3jljuq84o6UuKYvAKsdMKjBESQeRS3NCYEhIAQcE7g8pUoDBk9F0/UehOVQzqjbpP3lPGeaYNGzMZf56/YVBJ+5gJWr99l1w4cPmUuf/T4GfQdMh3nLkSY0xzdPPjnH0Rdu6EEoS4MHV1jYm47qgZ37sRi+c/b8W6/yajXrJeyxi36YuDwWdh38CTYjkNnFzLiMyYXqkuGItKkEABEkMlvgRAQAkLASwgcPfEnXmw7CFe0WbGFc4di/5a5OLzjC2W8ZxoF0isdhoBljd3etfcYxk752sLGTPoK74d+gm8XrTMWdfk+KuoGWnYYqgShLgwdXUdP/NJuvYePnkaDl9/HR5O/RtFCedGvRxtl77z9MmJj7+H1LiPR6b1xuBoZbeHPGcH23UajXLV2dm3j1r0W5eVBCPg6ARFkvv4JSv+FgA8QkC66RmD7r4eQIX0AhvZrj9IlCyFtWj+zI++ZNmLQW8gRnBUsa87Ubl59KQTrlky0sJ++G4Onnyit5Vr+e/fuPU1oDVFCZ86CFZaZdp56d2upRKEuDu1dRw3uZONJ8ThwxCzUrv4E1iyZgN7dW6JhSGVlLzSqhvEjuuOnb8fi/MWrmL3gJzx8+NCmji4dmmLj8slm+3H+cOTKEWRTThKEgK8TEEHm65+g9F8ICIEUQyAoKBNu3rqDC5ciHY7p7LkruHg5EpkzZ7AoY2/Jct2mPbgaFW1Rjg/pA/wxc1IfJXJat6jHpCSxi5ej1NJow/9VAtu010jhgrlRsUJJHDtxFnfuxtoUyRCYHjlzBJktOFsW+Pn9J1RtHCRBCPgogTQ+2m8v67Z0RwgIASGQeALPN6wGGpfxWr45FOOnfYdVa3aqfWHTZi0G05jXuN4zaNKoukWDG7bsRa9B0zBKWzoc++/S5aTPvlciJ2vWTBZlYQKCsmZWIoeCxzLTfU9Zs2RE1swZcTL8vN3ZL7YUc/MOzl2MUH0J8E/HJDEhkCoJiCBLlR+7DFoICAFvJMBZpCHacmXTxtVxQVvGi7oeg52/H8W23w6pWTGmMW/khx0RGBhgM4S8ubPj+3lhFsuWXMbs914bi7KxsX9jxrxlGDJmHrbsOGCR586H/Hlz4I1WjTBlxg9qA//xk2fBvWFcmrwefRM87dm+2yiEn7mI9q0by8yXK/ClTIolIIIsxX60MjAhIAR8mUCJovkx6P22COvfQRnvmRafMVH88FTkyfBzWLNhtzotGR//xJY1mUxopwmtr2aGggKsRfvB6uRo+ertUaNxd3B/2TOVHsPiBSNQrmzRxDYn/kLApwmIIPPpj086LwRSHIFUOSBuaucpRc5Y0XbvO44/Tp/HyPFfqlkspvGeaczjM40+9NWhcW8ZT0GW+/dkIkNl8LlFu8EY/8l34P4zlg0ISIfOHZoqoVerWgUmObUJny5UBwD0eu1d23cbrWa/rCsymUyoUK44po/vjYPbPrc4HLBz9XR80KO1Wq609pNnIZDaCIggS22fuIxXCAgBrydQrUp51KvztM0pS6Yxz94AuDnfeBqR97vWz/Q4RVIAABAASURBVFACiCEzfv5hHJ5+spQ9V4dpwcFZsHDeULX5n/XRRg/upE458rQjn3WbNPpdBKZ/tIz64MED7NpzTO19cxQbzVF6+JkLDvsjGUIgJRMQQebpT1faEwJCQAhYEeBeqwG9/lue5DJlaJ830KPTy3in40vKeM805ulGH/qyOm7ON55G5H60w0fPmEURw2QwDEXVSuWwetHHKF2iIN2cml+aNOCpRmO9WTJnUHu9rNODsmaCyWRS9d27dx/fLV5vERNNP2jAmT3rwwd6Hq+Mp6YqkR9CIJUREEGWyj5wGa4QEALeTeCUtlT5RteRKlI/lxtffXMoWnUMQ8iLvVQa81jG0SjOnL2ENm8PQ7VG3dB70DSzKOJ+rVrPvQvu4wr/86LF7JujuhKazgMHHw/vZnO4YN2SiRg9+G04OnzAfMZTM7Y7fd5SFdlfj/DPoLhcmjWWkXv7BCTVtwiIIPOtz0t6KwSEQAomwOj7r3UegTy5smPziilqz9X6ZZOUsOGyI9NKFiuAtp1H2kTqJxaGkBgwbCYCAvyV/5ZV05QvhQ6XFnevn4lGIZXRd/B0nD57kS5eawyB0b3jSxj14dsqsn+/fyP8D9RmEieOfAdlSxfx2r5Lx4RAQgiIIEsINfERAkLACwikvC5cvhKFQE1M9er2CrIHZ7UZINM6vvEC0gekwxltlsu6wIWLEeDsWbtWjdRSo3U+Z65Caj+NmJu38ac2k2adrz/fuROLPqGfWsxM6TNUA4bNUiE4OFOlpxmvXKrU60nMlcFfK1cso6L669H9jdfcObMlpnrxFQJeR0AEmdd9JNIhISAEUiuB3LmCcTf2b8ye/xMYJsKaA4XSD0s34tbtuyhUMI91NgoWyIXHtJmjuV+txLkLETb5rPOLb35WwVpLaDNtNgX+TfD3TwsuHeqzUsYr969xhoozVcZ0/b7yU2X+rUUuQkAIxIeACLL40PJwWWlOCAiB1EWgbKnCmDK2B3bvO67idFVr2M08S8X7SiGd8Mv6Xfjk414oV8Z2yY4b+7l3K0dwEBo17wOW12ev6M/YX+cuXMGsyX1RIF9Oh3Djmp0yzlRZ3xcrks9hvZIhBISAYwIiyByzkRwhIASEgMcJcIZp6VejwJAVi+YPA09W0njPtJ++HQOWcdSxHNmzYsLI7tizaTZWaGWHD3hL1aH7fz1rMIoXze/IPcnTufeLbyOwfhdnYhpmnePCujoVmYmpPxX4yhC9gIAIMi/4EKQLQkAICAFrApztypcnB+rWfEoZ75lmXc7RMzfFcwm0+jPlE+TvqN7EpnPvF4PRMixHYuvS/VlnSO2K4Lsz9TS5CgFfIyCCzNc+MemvEBAC8ScgHkJACAgBLycggszLPyDpnhAQAkJACAgBIZDyCSRakB0/cQrLVqy2sM1bd2KTwa5H33BI8mpklIUv61qzfrOF/59nzzn0lwxFQH4IASEgBISAEBACPkwg8YLspK0g23/wCCjKdIt2IsgiI6/ZCLKdv+2x8D8jgsyHf8Wk60JACAgBIZByCMhIkopAogVZUnVM6hUCQkAICAEhIASEQGohIIIsBX/Sd2PvYcuOA7gccS1ZRhl94xY2b98PXpOlA9KoEEgAAXERAkJACCQHAY8IshN/hGP1uk1Yu34LFnz9g4Vt27krOcadYtvcuHUv6jfrjYir1xETcxthYz/H0eNnLMYbe+9vlc8ycdntO3ctfPWH+/cfgG0NH/cFhoyZh/HTvlOvbHn48KFeREUKD/voc3U1J8qNEBACQkAICAEhYEPAI4IsKuo6Ll2OQGTUNXA/mNFu3bpt06nkTvhm0Vp8OmcJHIkRzjzx1SYs9+DBAyxavkmJEgoTGkXK8p+32331CcdG0cL3zY2e+CVeaNVfReLu1PNjrF6/C6ybZRzZjl2H8XqXkYi6dsNRkTjSgR2/HULdJu+5ZNt/PWRTH0Vc284jEDpyDjJmCFRBKs9djECztoPA17JwfDZOhgT2nWOo16yXGruzK9+nx9fFGNzlNgkIRFyLxQ9rziZBzVKlEBACQkAIuELAI4IsMDA98uTOieDgIBQpVMDCcudy/PoOJNM/QVkyYeYXy3HshP3/QB07eRbTZi8GXy9C+33vcfyoibIt2vLc1p0HlLDqHzYDdV7ogbUbd1uMguLiQ03ING0zEEtXbUPpEgVRs2oFXL9xE70GTUOLdoMRfuaChY/xIVZbhrx4KRIPHvxjTI73ffr0/lg4LwyHd3zh1OrXrWRT9zKt33wn3rdzh6J395Z4oVE18N12o0I7YfaCFTht56XHxkoyZEiPTu2aQH/3naNr/rw5cDUyGg+1/xn95d79BDbtvozNv18BhZn7a5cahYAQSJUEZNDxIuARQfbE44+hYb06aBBSG6+3aWFhzItXjz1Q+PFyxREclFntv7LX3LadB1V+9SrlzdlPP1EaP303BuuWTMSWVdOw/ZdPUfOZxzFUWzL8I/y8KscZN4qun9f9io/CumDbz59g/IjuCOvfAQs1cbP6x/GgWJk0/QfcvXtP+XjjD87uVaxQEhRMxv7p77CLjHI+e8cI3YzUbf0OPOvnAnm9T6wbx5uS7nUxduRUdLIMi+Fv+oeOwrhJ05OlfWlUCAgBIZDcBDwiyJJ7kPFtn0Kjmia21m3eg2vXYyzcb8TcwiZtJuzpJ0sjb+5gizzjA1/h0bPbK7ivLWnuOXBCZXEZc/tvhzFmcGc837Aa/NJY4me786b1x0fDuoAzWMopjh8P/vlHLV9yGZF2I8a1JeDY2L8xY94yi6VWLrcabcKnC9U+NOsulH+sGPYcOIk//7pszuIy5c7dRxAQkA5582RX6Ux7+M9/e8pUYjx/5MqZDYHpA+LpJcXjQ4CzYjT6UJjx6mljPEOKMl4pzDzdfgLbEzchIASEgNsIWCqCBFRbvWol9O3Z1Wwvv/gscuQMBme+3tBmw2iFtWVKR1Vnz57Nwrdu7eqoUL4s6Kcb63LknxTpJpMJz9Z/RhMcl8DlSWMbh4+dwXFtyfLF52qCy5XGPOv7IG3pM1OGQCVqYm7ewZIVW9EopDJCaj9lXdT8nDFDenAGyZwQx02UNhvVssNQ836wAcNmxuGR+OwmjWugbOnCeKFVP7zzwSQl6rjUOm3WIvTs8goK5MupGrkaeR3RmoBVD1Y/7B0s2LXnmFru5V46GvelpfVLA5PJZOUtj+4ksGjtf0vzR8Kjk2XZsnSp4qBxXFcjoyCijCTEhIAQSE0E0iR2sDmyB6s/pPxjSkubNi3+vndfm+EJAIUYzVkbRn/6/qPN+HDPGf10C8qaxVkVSZJXtlQhFMyfC5wl40wPG+GVz0xnPtOcGfeF3bx9B5kzZ8CFixHqFGKdGk/GKeSc1WmdlzNHENYumWDeB/bJuJ7WRew+cyarc4emarmUS6b2rHe3lqrv1hVkzhSICdpS6/JvxuCpCqVA0dS+zbPYsGwymjSubl3c5nnhkg2oWKejWUTygMHLr3+I/sNmYOyUrzFl5iKs2bgb4Wcu2vhKgnsJcGZs0+4rFpUaBZpFRhI+8O9Ah9dfVX9L2IyIMlIQEwJCIDURSLQgs4aVxpQGAf7+CZrVSIyvdT8S+5w9OCu4R2znrsNqSZD1RV27AT4znflMs2cUbmfPXQZPW2bQlttY/v6Df8DlxUwZ09tz8Yk0joub+bk0ejUyGpzNa6oJsC4dXkSVimVwRJs95MzWtFmLsWHLXodj4uzirvUzzCKSBwu4727dkolqD95P345B2IAOKFE0PyjSHVYkGS4RiLgWC8588RTlZ9+fBG34jEPoMWY3hs84aFMHBdqjvENa/iFVnr401mXj4KYEEWVuAinVCAEfJCBdBtwuyC5euowTf4Tj0iXLb92uwE6Mryv1x7dM43pVcPFyJI6eeLSkc+BwOHjC8bmGVW2q2rX3GCqHdEa5au1Qvnp7PPvKB7gScR1Txr5nXsKzcUrGBB4aaNlhiOov++zI5ixYYe7lvb/vY4C2JMoZLWtr2LwPQkfPwWefL8PliChNkJvdbG4C/NMhQ6BzYcrTqJeuRKFwwdyQfxJHIGe2R3vwuD+MYotGgUZxRbNXO9NZhsbyi9b+haPhN6DXZc/HHWm6KOOV9XGmbJxs9CcKMSEgBFI4AbcLspTEq2Txgiil2aq1v4KBUFeu2YlSJQqieJH8NsMsWjgvxgzprMI/MATE8m9GY8XCsShftqgqmyN7VgQHZcH+Q6fUszt/xMTcxumzF8GI+Ddv3Y2zah5Y2Lh8Mlyx1i3qmeujkJo+vrfFzFZvbVkzb+7sWLt4gprd+nH+cAwf+Bbq1nzK7JeQG47lRswtFC+aLyHu4mNF4LFiWRHa+fEEC6rm9Qtq/v+dKraq3q2PFGPcm6pXGhl5Tb/14at0XQgIASHgnIAIMid8uFeqZtXH8dvvR3Hg8Cn8vu84mmhLdEy3dsuhLXHWq1MReuiGYkXywS/Nf3hz5QhCnZpPguLu/MWr1u7xeuasHWeo9Fmtqg274oVX++PgkXBc1maV4qqMwop7z1yxuGayjG1xo/7cr1aqTf48rfnV92uN2fG6Z10Uw/kk9EW8uDkrzNmthIiy0M7l0aJBIWdVuzVv245dWLZitblO7i0zP8iNEBACQiCFEvhPMaTQASZ2WJzpib5xE59//TMYRb9yxTIJqtJkMqHVSyG4eesOPhw5G9E3btnUwz1aFGx9B0+3m0+HsqWLmGfhZk3qi/VLJ2LLyqk4sG0eKB5ZJjmMbXJz/+Nli6FGlfLKypYqzOQEGX0//3SANkNZIEH+4mSfAEXZlP6VUKdSLvsFrFIpxji7ZpWcZI8MezFvwXfm+vv27Gre6G9OlBshIASEQAokkGhBxj0e/COq29/37yM4WxAyZsqIP8+eU3Y92nmgUKMvT1QGBAQoP1f9k/JzKVo4Dx7TRNC6zb+jytNlUUxbmkxoeyWK5ce4YV1x9MSfaP5GKBYu2YALl66q90ruO3gS7/abDL4qyM8vDfzTpbXbTO6c2cyzcNWfKY/cuYI13lksZuPsOmqJJ06dw0ttB6GeC68sMpahD321Kpz+6+fnBwpWfZaw4hMlLcozMG77bqPj3Lemz/wZr8a9bBaVykOCCDSvH/eMF0Wbp8WYcb+YiLEEfbTiJARSOoEUO740iR3Z9p27wT+iuvGZoSsOHzmO+V//oCzaiSCjGDP67j94BMdPnlJ+uj/TEtvPhPpzyY4Cg/6N/lcZFB28T6hVq1wOS78ciQrliiNs7Odo8NL7KvzDa51GYP/BPzDo/dcxYlBHBAY+2oid0Hbs+VHMvdupeZyvLOrXo41FGfrQ116d8UkLTB+ASaPfdWnv2karPW6tDXvZ4tOmlLVP4IgLEfkjomLtOydBqv53QK9axJhOQq5CQAikFgKJFmSpAVSbFvXVRvZnG1S1O9xRgzuBy2sUb3YLWCVyVmvCyO7Ys2m2WZzwNUqbtaVHtpVr0rPmAAADvklEQVQ2rZ+Vh+uPPHTAU6DpA/xtnPj2gJDaFc0zbBSarhh96GtToZaQKVMgGJnfT5vV0x6d/msymRCUNRNc2btmXcZVtk47IJlmAhHX4j78ccSDQWI50653LtWLMR2EXIWAEEhVBDwiyBgGY/W6TVi7fgsWaLNmRtu2c1eqAm4crHFzPYWKyWQyZifovla1CuDJRwajpQ3p1x7cd5agylxwevWlECz4bJBaNrUuznbHhXX1yrAf1n1Nbc9Hwy23EXB5sssrJW1OYboyk+YOdgwqzc37Y4YPlD1j7gAqdQgBIeBzBDwiyKKiruPS5QhERl3DmbPnLOzWLdfevehzZL2gw5wlo0Bzx3JjQobDdu3MriWkKvFxI4GIfwPFskpu8ufGfYoxijJ9wz/TmR/hwkwayyXWGOqiRrXK4DWxdYm/EBACQsAXCXhEkPFVSHly50RwcBCKFCpgYblz5YT8IwSEgOcI6CKLscUowKw37lOcdWlZEky3nknzXC+lJSEgBIRAYgn4lr9HBNkTjz+GhvXqoEFIbbzepoWFMc+3kElvhYDvE6AQcxZbjGKMM2e1n3YtPIbvE0n+ESxavknF8Fu1ZqfTzuzed1yVY8w/xutj4S07DqBjj4/UqW0+iwF828dn85bhy4Vr8ODBA7tI+Cq4CZ8sxC/rf0PMzTsYOGwm5n/3CxiCyK6DBxP52fIz5u+FvWYZz3L0xC/x0ZRv1El9e2WYxtPtn85Zon5njp189NYZprvLWCf7wf44q1N+R53ReZTnEUH2qCn5KQSEgDcQoNjSlyTj6g+XMeMqI/nuIfD73uP4YelGTNdExLXrMXYrZSzEmZ8vV+U2b9sPXWjs2HUYv/5+BOcvXLXrl1SJjKe4fvMeXI645pYmOD7+hzv8zIVE18eT6uQza/5yXLwUZbe+Hb8dwryvVyJL5oy4GnUdW3YexO49x8HXxNl1MCQyWPiuPcccij1D0QTdsu/8jPl7Ya8Ciskflm3CF9/8jA1b99orotL27D8JCjL+bl26HKnS3PmDdbIf7I+zepPrd9RZn7wtTwSZt30i0h8hIARSLQGTyYTTf17A4WNn7DI4dfoCGLPQZLI8AMSDPFtXfYJKT5W265dUiecuRKDvkOk4etx+f+PbbkzMbRUOaMMWxwIjPnXWqPq4CrK979AfNm4UPOu1dsqXLQZa0UJ5sfK7sRg3vCt44MrGwSrh20Xr8MnsxeBMllWWRx9NJhPWbvxdBS63bpgzfavW/mqdnCzPyfU7miyDTWCj/wcAAP//Xb66AQAAAAZJREFUAwDQV3P4TrG62QAAAABJRU5ErkJggg==)

<div class="card" style="margin-top: 10px; padding: 24px; border-left: 6px solid #1a73e8;">
  <h3 style="color: #1a73e8; font-size: 24px; margin-top: 0;">📍 Compute Engine VM 인스턴스 메뉴 이동</h3>
  <p style="font-size: 19px; color: #3c4043; line-height: 1.6;">
    1. 좌측 상단 <strong>탐색 메뉴(☰)</strong>를 클릭합니다.<br>
    2. <strong>Compute Engine > VM 인스턴스</strong>를 클릭합니다.<br>
    3. 가상 머신의 생명주기(생성, 중지, 삭제, SSH 접속)를 일괄 관리할 수 있습니다.
  </p>
</div>

<!--
comment:
💬 [강사 대본]
"콘솔에서 가상 머신 페이지로 이동하는 순서입니다. 햄버거 메뉴에서 Compute 하위의 Compute Engine, VM 인스턴스를 선택하시면 수강생분들의 가상 머신 리스트와 상태가 한눈에 나타납니다."
-->

---

<!-- Page 6 -->

## 콘솔 활용 실습 가이드 02: 리소스 상태 확인

<div class="card-grid">
  <div class="card">
    <div class="card-title">🟢 실행 중 (Running)</div>
    <div class="card-desc">VM 인스턴스가 정상 작동 중이며 IP 주소 및 CPU 사용량 모니터링 가능</div>
  </div>
  <div class="card">
    <div class="card-title">🔴 중지됨 (Stopped)</div>
    <div class="card-desc">전원이 꺼진 상태. 컴퓨팅 요금은 청구되지 않으나 디스크(Persistent Disk) 비용은 발생</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"VM 인스턴스 리소스 상태 카드입니다. 초록색 아이콘은 VM이 켜진 정상 실행 중 상태이고, 중지된 상태에서는 CPU/RAM 비용은 중단되지만 보관 중인 디스크 요금은 지속되므로 사용이 끝난 인스턴스는 주의 깊게 보셔야 합니다."
-->

---

<!-- Page 7 -->

## API 액세스 및 Client Libraries

<div class="tool-hero-layout">
  <div>
    <ul>
      <li><strong>RESTful APIs</strong>: HTTP GET, POST, PUT, DELETE 메서드 기반 프로그래밍 제어</li>
      <li><strong>JSON 데이터 형식</strong>: 요청 및 응답 데이터 표준 포맷 사용</li>
      <li><strong>Google Cloud Client Libraries</strong>: Java, Python, Node.js, Go 등 최적화 SDK 제공</li>
      <li><strong>OAuth 2.0 보안 인증</strong>: 안전한 API 호출 및 토큰 인증 메커니즘 지원</li>
    </ul>
  </div>
  <div class="tool-icon-box">
    <img src="data:image/png;base64,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" alt="Cloud APIs">
    <div class="tool-icon-name">Google Cloud APIs</div>
    <div style="font-size: 14px; color: #5f6368; margin-top: 6px;">RESTful APIs & SDKs</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"개발자나 엔지니어가 애플리케이션 코드 내부에서 GCP 서비스를 제어할 때는 REST API 및 Client Libraries를 활용합니다. Python, Node.js, Java 등의 언어로 손쉽게 인프라 조작 코드를 작성할 수 있으며, 모든 통신은 OAuth 2.0 표준 토큰으로 보안 인증됩니다."
-->

---

<!-- Page 8 -->

## Cloud Shell (통합 CLI 터미널)

<div class="tool-hero-layout">
  <div>
    <ul>
      <li><strong>브라우저 통합 터미널</strong>: 별도 로컬 CLI 설치 없이 GCP 콘솔에서 클릭 한 번으로 즉시 접속</li>
      <li><strong>5GB 영구 홈 디렉토리 ($HOME)</strong>: 파일 및 자동화 스크립트 영구 보관</li>
      <li><strong>사전 설치된 개발 도구</strong>: gcloud, gsutil, bq, kubectl, Docker, Terraform 기본 탑재</li>
    </ul>
  </div>
  <div class="tool-icon-box">
    <img src="data:image/png;base64,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" alt="Cloud Shell">
    <div class="tool-icon-name">Cloud Shell</div>
    <div style="font-size: 14px; color: #5f6368; margin-top: 6px;">Free 5GB Linux Web Shell</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"로컬 PC에 gcloud를 설치하지 않고도 브라우저 안에서 5GB 영구 디렉토리와 함께 gcloud, kubectl, Terraform이 모두 깔려있는 Cloud Shell 터미널 환경을 경험하실 수 있습니다."
-->

---

<!-- Page 9 -->

## 실습 01 안내: 콘솔 및 Cloud Shell 활용

<div class="card" style="margin-top: 20px; padding: 30px; border-left: 6px solid #1a73e8;">
  <h3 style="color: #1a73e8; font-size: 26px; margin-top: 0;">🧪 Lab 01. Interacting with Google Cloud</h3>
  <p style="font-size: 20px; color: #3c4043; line-height: 1.6;">
    • <strong>Task 1</strong>: Google Cloud Console 웹 UI를 활용하여 Cloud Storage 버킷 생성 및 파일 업로드<br>
    • <strong>Task 2</strong>: Cloud Shell 터미널에서 `gsutil` 명령어 및 `gcloud` CLI로 동일 작업 수행 비교<br>
    • <strong>Task 3</strong>: Cloud Shell의 5GB 영구 홈 디렉토리 및 에디터 기능 체험
  </p>
</div>

<!--
comment:
💬 [강사 대본]
"첫 번째 실습 과정인 Lab 01 안내입니다. 웹 콘솔 UI로 Cloud Storage 버킷을 만들어 보고, 똑같은 작업을 Cloud Shell 터미널의 gsutil 및 gcloud 명령어로 실행하며 두 인터페이스의 차이를 직접 비교해 보겠습니다."
-->

---

<!-- Page 10 -->

## 실습 01 상세 목표 및 비교 분석

<div class="card-grid">
  <div class="card">
    <div class="card-title">🌐 Task 1: 웹 콘솔 실습</div>
    <div class="card-desc">`console.cloud.google.com`에서 마우스 클릭으로 스토리지 버킷을 생성하고 파일 드래그 앤 드롭 업로드</div>
  </div>
  <div class="card">
    <div class="card-title">💻 Task 2: Cloud Shell CLI 실습</div>
    <div class="card-desc">`gsutil mb gs://[BUCKET_NAME]` 및 `gsutil cp` 명령어로 동일한 버킷 생성 및 명령어 제어</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"실습 1의 핵심 비교 포인트입니다. 동일한 버킷 생성을 마우스 클릭과 CLI 커맨드로 각각 실행해 보며 콘솔의 직관성과 CLI의 스크립트 자동화 유용성을 체험하실 수 있습니다."
-->

---

<!-- Page 11 -->

## 베스핀글로벌 실습 환경 접속 수칙

<div class="alert-warning-box">
  <div class="alert-warning-title">🏢 실습 환경 자격 증명 (Bespin Global Lab Environment)</div>
  <div style="font-size: 19px; color: #5c3c00; line-height: 1.5;">
    • <strong>조직 (Organization)</strong>: `bespin.email`<br>
    • <strong>지정 프로젝트 (Project)</strong>: `KDT5T`<br>
    • <strong>주의사항</strong>: Qwiklabs 계정을 사용하지 않으며, 부여된 계정으로 Google Cloud Console에 로그인하여 지정된 `KDT5T` 프로젝트 내에서만 실습을 수행해야 합니다.
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"저희 실습 접속 수칙을 다시 한번 알려드립니다. 퀵랩 계정이 아닌, 안내받으신 계정으로 로그인하시고 반드시 조직 'bespin.email' 하위의 지정 프로젝트 'KDT5T'를 선택하여 실습해 주세요."
-->

---

<!-- Page 12 -->

## 실습 02 안내: Google Cloud Marketplace

<div class="tool-hero-layout">
  <div>
    <ul>
      <li><strong>오픈소스 & 엔터프라이즈 자동 배포</strong>: 검증된 솔루션을 클릭 몇 번으로 자동 배포</li>
      <li><strong>실습 수행 과제</strong>: Marketplace를 통해 Jenkins (CI/CD 자동화 서버) 또는 LAMP 스택 1-Click 자동 인프라 배포 수행</li>
    </ul>
  </div>
  <div class="tool-icon-box">
    <img src="data:image/png;base64,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" alt="Marketplace">
    <div class="tool-icon-name">Cloud Marketplace</div>
    <div style="font-size: 14px; color: #5f6368; margin-top: 6px;">1-Click Deploy Solution</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"두 번째 실습인 Cloud Marketplace 자동 배포 실습입니다. 복잡한 설치 과정 없이 클릭 한 번으로 Jenkins CI/CD 서버나 LAMP 웹 스택을 인프라 위에 1-Click 자동 구성하는 강력한 기능을 경험해 봅니다."
-->

---

<!-- Page 13 -->

## 실습 02 상세 세부 수행 단계

<div class="card-grid-3">
  <div class="card">
    <div class="card-title">1. Marketplace 솔루션 검색</div>
    <div class="card-desc">검색창에서 Jenkins 검색 후 [LAUNCH] 클릭</div>
  </div>
  <div class="card">
    <div class="card-title">2. VM 사설 구성 및 자동 배포</div>
    <div class="card-desc">Compute Engine 머신 유형 설정 및 1-Click 자동 인프라 배포</div>
  </div>
  <div class="card">
    <div class="card-title">3. SSH 접속 및 웹 UI 검증</div>
    <div class="card-desc">External IP로 웹 서비스 접속 및 SSH 터미널에서 서비스 상태 확인</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"실습 2 수행 순서입니다. Marketplace에서 Jenkins를 검색해 배포 버튼을 누르면 구글이 VM 생성부터 소프트웨어 설치까지 자동으로 처리해 줍니다. 완료 후 웹 브라우저 접속과 SSH 터미널 상태를 직접 확인해 봅니다."
-->

---

<!-- Page 14 -->

## 🚨 실습 시 필수 보안 & 비용(FinOps) 관리 수칙

<div class="alert-danger-box">
  <div class="alert-danger-title">🚨 Service Account Key & API Key 절대 보안 수칙</div>
  <div style="font-size: 19px; color: #5c1d1a; line-height: 1.5;">
    • <strong>Service Account Key JSON 파일 및 API Key를 Public망이나 GitHub 공용 저장소에 절대로 올리지 마세요!</strong><br>
    • 키 노출 시 봇(Bot)에 의해 즉시 해킹당하여 <strong>수천만 원 상당의 비용 청구 폭탄</strong>이 발생합니다.
  </div>
</div>

<div class="alert-warning-box">
  <div class="alert-warning-title">⚠️ VM Off 및 요금 집계 48시간 시차 인지</div>
  <div style="font-size: 19px; color: #5c3c00; line-height: 1.5;">
    • 실습 종료 후에는 항상 <strong>Compute Engine VM 전원을 중지(OFF)</strong>해야 합니다.<br>
    • GCP 요금 집계 데이터는 <strong>최소 2일(48시간) 시차</strong>가 있으므로 비용 절감을 항시 인지해야 합니다.
  </div>
</div>

<!--
comment:
🚨 [강력 보안 & 비용 강사 대본]
"매 매우 중요한 필수 실습 수칙입니다! Service Account 키 파일이나 API 키를 절대로 GitHub 등 퍼블릭 망에 올리지 마십시오. 봇에 해킹당해 어마어마한 비용 청구가 발생할 수 있습니다. 또한 사용이 끝난 VM은 즉시 OFF로 끄셔야 하며, GCP 요금 반영은 최소 48시간 뒤에 나타난다는 점을 명심해 주세요."
-->

---

<!-- Page 15 -->

## 복습 퀴즈 01 (Review Question 1)

<div class="card" style="margin-top: 20px; padding: 30px;">
  <h3 style="color: #202124; font-size: 24px; margin-top:0;">❓ Q1. 다음 중 Google Cloud와 상호작용하기 위해 사용할 수 있는 기본 관리 인터페이스 2가지는 무엇인가요?</h3>
  <p style="font-size: 20px; color: #3c4043; line-height: 1.8;">
    A. console.cloud.google.com 웹 브라우저 기반 GUI인 <strong>Google Cloud Console</strong><br>
    B. 특정 지역 전용 Google Cloud Wi-Fi 전용 접속기<br>
    C. 명령어를 수행하고 스크립트 자동화를 지원하는 <strong>Google Cloud SDK & Cloud Shell</strong><br>
    D. 음성 인식을 지원하는 AI 전용 하드웨어 단출 장치
  </p>
</div>

<!--
comment:
💬 [강사 대본]
"모듈 01 복습 첫 번째 퀴즈입니다. Google Cloud와 상호작용하기 위해 제공되는 기본 대표 인터페이스 2가지는 무엇일까요? 선택지를 잘 읽어보시고 정답을 골라보세요."
-->

---

<!-- Page 16 -->

## 복습 퀴즈 01 정답 및 해설

<div class="card" style="margin-top: 20px; padding: 30px; border-left: 6px solid #34a853;">
  <h3 style="color: #34a853; font-size: 26px; margin-top:0;">✅ 정답: A, C</h3>
  <p style="font-size: 20px; color: #3c4043; line-height: 1.7;">
    • <strong>A (정답)</strong>: `console.cloud.google.com` 웹 브라우저를 통한 그래픽 UI 인터페이스인 Google Cloud Console이 정답입니다.<br>
    • <strong>C (정답)</strong>: 터미널 환경에서 `gcloud`, `gsutil` 등의 커맨드라인 CLI 및 자동화를 지원하는 Google Cloud SDK와 Cloud Shell이 정답입니다.<br>
    • <strong>B, D (오답)</strong>: 특정 Wi-Fi 장치나 전용 음성 하드웨어 단말기는 GCP 관리 인터페이스가 아닙니다.
  </p>
</div>

<!--
comment:
💬 [강사 대본]
"정답은 A번과 C번입니다! 웹 브라우저로 접속하는 그래픽 콘솔(A)과 CLI 터미널 환경을 제공하는 Cloud SDK 및 Cloud Shell(C)이 구글 클라우드의 대표적인 상호작용 인터페이스입니다."
-->

---

<!-- Page 17 -->

## 복습 퀴즈 02 (Review Question 2)

<div class="card" style="margin-top: 20px; padding: 30px;">
  <h3 style="color: #202124; font-size: 24px; margin-top:0;">❓ Q2. Google Cloud Console과 Cloud Shell의 결정적인 차이점은 무엇인가요?</h3>
  <p style="font-size: 20px; color: #3c4043; line-height: 1.8;">
    A. Google Cloud Console은 터미널 CLI 환경이고, Cloud Shell은 웹 GUI이다.<br>
    B. <strong>Cloud Shell은 브라우저 내 터미널 CLI 환경이고, Google Cloud Console은 웹 GUI 인터페이스이다.</strong><br>
    C. Cloud Shell은 사용자 로컬 PC에 직접 설치하는 프로그램이다.<br>
    D. 두 도구는 기능이 100% 동일하므로 차이점이 전혀 없다.
  </p>
</div>

<!--
comment:
💬 [강사 대본]
"두 번째 복습 퀴즈입니다. 콘솔(Console)과 클라우드 셸(Cloud Shell)의 핵심 차이점을 묻는 질문입니다. 차이점을 명확히 떠올려 보세요."
-->

---

<!-- Page 18 -->

## 복습 퀴즈 02 정답 및 해설

<div class="card" style="margin-top: 20px; padding: 30px; border-left: 6px solid #34a853;">
  <h3 style="color: #34a853; font-size: 26px; margin-top:0;">✅ 정답: B</h3>
  <p style="font-size: 20px; color: #3c4043; line-height: 1.7;">
    • <strong>B (정답)</strong>: Google Cloud Console은 마우스 클릭 중심의 웹 GUI 화면이며, Cloud Shell은 5GB 영구 디렉토리가 제공되는 브라우저 통합 CLI 터미널 환경입니다.<br>
    • <strong>A (오답)</strong>: 설명이 서로 반대로 기재되었습니다.<br>
    • <strong>C (오답)</strong>: Cloud Shell은 로컬 PC 설치가 필요 없고 Google 클라우드 인프라가 제공해 주는 웹 터미널입니다.<br>
    • <strong>D (오답)</strong>: 그래픽 UI와 커맨드라인 CLI의 명확한 역할 차이가 존재합니다.
  </p>
</div>

<!--
comment:
💬 [강사 대본]
"정답은 B번입니다! 콘솔은 직관적인 웹 GUI 화면이고, Cloud Shell은 브라우저 안에서 5GB 스토리지를 무료 제공하는 CLI 터미널입니다. 상황에 맞게 2가지 도구를 혼용해 사용하는 것이 베스트 아키텍트입니다."
-->

---

<!-- Page 19 -->

## 모듈 01 요약 및 정리 (Module Summary)

<div class="card-grid">
  <div class="card">
    <div class="card-title">📌 다각도 관리 인터페이스</div>
    <div class="card-desc">Google Cloud Console(GUI), Cloud SDK & Cloud Shell(CLI), REST APIs, Mobile App</div>
  </div>
  <div class="card">
    <div class="card-title">💻 Cloud Shell의 강력함</div>
    <div class="card-desc">로컬 미설치, 브라우저 내 5GB 무료 영구 디렉토리 및 gcloud pre-installed</div>
  </div>
  <div class="card">
    <div class="card-title">🚀 Marketplace 자동화</div>
    <div class="card-desc">검증된 오픈소스 소프트웨어 및 앱 인프라 1-Click 자동 배포</div>
  </div>
  <div class="card">
    <div class="card-title">🛡️ 보안 및 비용 철칙</div>
    <div class="card-desc">API/Service Account Key GitHub 노출 금지 & 미사용 시 VM OFF 필수</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"모듈 01에서 배운 내용을 요약 정리해 보겠습니다. 콘솔, CLI, REST API, 모바일 앱이라는 4가지 상호작용 도구를 살펴보았고, 5GB 스토리지가 포함된 Cloud Shell과 1-Click 배포인 Marketplace, 그리고 보안 및 VM OFF 수칙을 다루었습니다."
-->

---

<!-- Page 20 -->

<!-- _class: lead -->

<div class="cover-header-logo">
  <img src="https://www.gstatic.com/images/branding/product/2x/google_cloud_64dp.png" width="48" style="box-shadow:none; border-radius:0; border:none;">
  <span class="cover-header-text">Google Cloud</span>
</div>

<div class="badge badge-cover">NEXT MODULE PREVIEW</div>

# 감사합니다!

### 다음 장표: Module 02. Virtual Networks (VPC 가상 네트워크)

<div class="cover-footer-info">
  Google Cloud 교육 자료 | 베스핀글로벌 2026 개정판
</div>

<!--
comment:
💬 [강사 대본]
"이상으로 모듈 01 수업을 마치겠습니다! 수고 많으셨습니다. 10분간 휴식하신 후 다음 모듈 02에서는 Google Cloud 인프라 아키텍팅의 핵심인 VPC 가상 네트워크와 서브넷 구축에 대해 다루어 보겠습니다. 감사합니다!"
-->
