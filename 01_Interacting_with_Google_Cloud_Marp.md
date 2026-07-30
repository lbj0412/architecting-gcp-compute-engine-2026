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
  
  /* 표지 타이틀 슬라이드 (Google Cloud Dark Navy Theme - Standardized Layout) */
  section.lead {
    background: linear-gradient(135deg, #0b3880 0%, #1557bf 100%);
    color: #ffffff;
    padding: 80px 60px;
    text-align: left !important;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start !important;
  }
  section.lead header {
    color: #ffffff !important;
    font-weight: 700;
  }
  section.lead footer {
    color: #e8f0fe !important;
  }
  
  section.lead h1 {
    color: #ffffff;
    font-size: 50px;
    font-weight: 800;
    line-height: 1.2;
    margin-top: 10px;
    margin-bottom: 12px;
    letter-spacing: -0.03em;
    text-align: left !important;
  }
  section.lead h3 {
    color: #e8f0fe;
    font-size: 22px;
    font-weight: 600;
    margin-bottom: 18px;
    letter-spacing: -0.02em;
    opacity: 0.95;
    text-align: left !important;
  }

  .cover-brand-header {
    display: flex;
    align-items: center;
    gap: 14px;
    margin-bottom: 10px;
    align-self: flex-start;
  }
  .cover-brand-title {
    font-size: 30px;
    font-weight: 800;
    color: #ffffff;
    letter-spacing: -0.02em;
  }

  .cover-guide-box {
    background: rgba(255, 255, 255, 0.15);
    border-left: 4px solid #ffffff;
    border-radius: 8px;
    padding: 12px 18px;
    color: #ffffff !important;
    font-size: 19px;
    font-weight: 600;
    margin-top: 15px;
    backdrop-filter: blur(10px);
    max-width: 580px;
    text-align: left !important;
    align-self: flex-start;
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

![bg right:42% fit](https://images.unsplash.com/photo-1544197150-b99a580bb7a8?w=800)

<div class="cover-brand-header">
  <img src="https://www.gstatic.com/images/branding/product/2x/google_cloud_64dp.png" width="52" style="box-shadow:none; border-radius:0; border:none;">
  <span class="cover-brand-title">Google Cloud</span>
</div>

# Interacting with<br>Google Cloud

### 2026 Modernized Edition | Module 01: Interacting with Google Cloud

<div class="cover-guide-box">
  Google Cloud 콘솔, Cloud Shell, SDK, REST API 및 모바일 앱 다각도 관리 가이드
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
    <div class="card-title">🖥️ 1. Google Cloud Console</div>
    <div class="card-desc">웹 브라우저 기반 GUI 관리 인터페이스 (`console.cloud.google.com`)</div>
  </div>
  <div class="card">
    <div class="card-title">💻 2. Cloud Shell & Cloud SDK</div>
    <div class="card-desc">gcloud, gsutil, bq 커맨드라인 CLI 및 5GB 영구 무료 터미널</div>
  </div>
  <div class="card">
    <div class="card-title">⚡ 3. REST-based APIs</div>
    <div class="card-desc">RESTful API (GET, POST, PUT, DELETE) 및 언어별 Client Libraries</div>
  </div>
  <div class="card">
    <div class="card-title">📱 4. Cloud Mobile App</div>
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

![bg right:40% fit](https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=800)

<ul>
  <li><strong>상단 좌측 햄버거 버튼 (☰)</strong>: GCP 전체 서비스 카테고리 탐색</li>
  <li><strong>주요 카테고리 구분</strong>:
    <ul>
      <li>Compute Engine, GKE, Cloud Run 등 컴퓨팅 제품군</li>
      <li>VPC network, Cloud DNS, Cloud Armor 네트워킹 제품군</li>
      <li>IAM & Admin 보안 및 권한 설정</li>
    </ul>
  </li>
  <li><strong>고정(Pin) 기능</strong>: 자주 쓰는 메뉴를 상단에 고정 가능</li>
</ul>

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

![bg right:38% fit](https://images.unsplash.com/photo-1516259762381-22954d7d3ad2?w=800)

<ul>
  <li><strong>RESTful APIs</strong>: HTTP GET, POST, PUT, DELETE 메서드 기반 프로그래밍 제어</li>
  <li><strong>JSON 데이터 형식</strong>: 요청 및 응답 데이터 표준 포맷 사용</li>
  <li><strong>Google Cloud Client Libraries</strong>: Java, Python, Node.js, Go, Ruby 등 최적화 SDK 제공</li>
  <li><strong>OAuth 2.0 보안 인증</strong>: 안전한 API 호출 및 토큰 인증 메커니즘 지원</li>
</ul>

<!--
comment:
💬 [강사 대본]
"개발자나 엔지니어가 애플리케이션 코드 내부에서 GCP 서비스를 제어할 때는 REST API 및 Client Libraries를 활용합니다. Python, Node.js, Java 등의 언어로 손쉽게 인프라 조작 코드를 작성할 수 있으며, 모든 통신은 OAuth 2.0 표준 토큰으로 보안 인증됩니다."
-->

---

<!-- Page 8 -->

## Cloud Mobile App (모바일 관리 전용 앱)

![bg right:38% fit](https://images.unsplash.com/photo-1512941937669-90a1b58e7e9c?w=800)

<ul>
  <li><strong>스마트폰 기반 관리</strong>: Android 및 iOS 전용 Google Cloud 모바일 앱 지원</li>
  <li><strong>실시간 모니터링</strong>: CPU, 네트워크 트래픽, HTTP 요청수 등 실시간 그래프 시각화</li>
  <li><strong>긴급 장애 제어</strong>: 이동 중 알림(Alert) 수신, 긴급 SSH 접속, VM 전원 중지/재부팅</li>
</ul>

<!--
comment:
💬 [강사 대본]
"야외에 있거나 이동 중일 때 긴급 장애 알림이 오면 스마트폰의 Cloud Mobile App을 이용해 실시간 그래프를 확인하고 VM을 재부팅하거나 SSH로 접속해 즉시 조치하실 수 있습니다."
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

<div class="card" style="margin-top: 20px; padding: 30px; border-left: 6px solid #1a73e8;">
  <h3 style="color: #1a73e8; font-size: 26px; margin-top: 0;">🚀 Lab 02. Deploying Infrastructure via Marketplace</h3>
  <p style="font-size: 20px; color: #3c4043; line-height: 1.6;">
    • Google Cloud Marketplace는 검증된 오픈소스 및 기업용 솔루션을 클릭 몇 번으로 자동 배포하는 서비스입니다.<br>
    • <strong>실습 내용</strong>: Marketplace를 통해 Jenkins (CI/CD 자동화 서버) 또는 LAMP 스택 1-Click 자동 인프라 배포 수행
  </p>
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

<div class="badge badge-cover">NEXT MODULE PREVIEW</div>

# 수고하셨습니다!

### 다음 장표: Module 02. Virtual Networks (VPC 가상 네트워크)

<div class="cover-guide-box">
  Google Cloud 글로벌 사설망 위에서 구동되는 VPC 네트워크 구축 및 서브넷 설계
</div>

<!--
comment:
💬 [강사 대본]
"이상으로 모듈 01 수업을 마치겠습니다! 수고 많으셨습니다. 10분간 휴식하신 후 다음 모듈 02에서는 Google Cloud 인프라 아키텍팅의 핵심인 VPC 가상 네트워크와 서브넷 구축에 대해 다루어 보겠습니다. 감사합니다!"
-->
