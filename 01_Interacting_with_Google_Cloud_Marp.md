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

<div class="card" style="margin-top: 20px; padding: 30px; border-left: 6px solid #1a73e8;">
  <h3 style="color: #1a73e8; font-size: 26px; margin-top: 0;">📍 Compute Engine VM 인스턴스 메뉴 이동</h3>
  <p style="font-size: 20px; color: #3c4043; line-height: 1.6;">
    1. 좌측 상단 <strong>탐색 메뉴(☰)</strong>를 클릭합니다.<br>
    2. <strong>Compute > Compute Engine > VM 인스턴스</strong>를 클릭합니다.<br>
    3. 해당 화면에서 가상 머신의 생명주기(생성, 중지, 삭제, SSH 접속)를 일괄 관리할 수 있습니다.
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
