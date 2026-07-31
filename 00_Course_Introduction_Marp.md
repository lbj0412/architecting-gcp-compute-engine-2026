---
marp: true
theme: uncover
paginate: true
header: ''
footer: ''
style: |
  /* 본문 내 모든 요소 강제 좌측 정렬 (표지/Q&A 제외) */
  section:not(.lead) p,
  section:not(.lead) ul,
  section:not(.lead) ol,
  section:not(.lead) li,
  section:not(.lead) div,
  section:not(.lead) .card,
  section:not(.lead) .card-desc,
  section:not(.lead) .card-title,
  section:not(.lead) h3,
  section:not(.lead) table {
    text-align: left !important;
  }

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

  /* 일반 슬라이드 제목 (H1 & H2) - 아래 파란색 밑줄(h2::after) 완전 제거! */
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

  /* 서비스 전용 브랜드 아이콘 래퍼 및 카드 스타일 */
  .service-hero-layout {
    display: grid;
    grid-template-columns: 1.2fr 0.8fr;
    gap: 24px;
    align-items: center;
    margin-top: 15px;
  }
  .service-icon-box {
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
  .service-icon-box img {
    width: 110px;
    height: 110px;
    margin-bottom: 16px;
    box-shadow: none !important;
    border-radius: 0 !important;
  }
  .service-icon-name {
    font-size: 24px;
    font-weight: 800;
    color: #1a73e8;
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
---

<!-- Page 1 -->
<!-- _class: lead -->

<div class="cover-header-logo">
  <img src="https://www.gstatic.com/images/branding/product/2x/google_cloud_64dp.png" width="48" style="box-shadow:none; border-radius:0; border:none;">
  <span class="cover-header-text">Google Cloud</span>
</div>

# Architecting with<br>Google Compute Engine

### 2026 Modernized Edition | Module 00: Course Introduction

<div class="cover-guide-box">
  Google Cloud 인프라 구축, 설계, 자동화 및 실습 가이드
</div>

<div class="cover-footer-info">
  Google Cloud 교육 자료 | 베스핀글로벌 2026 개정판
</div>

<!--
comment: 
💬 [강사 대본]
"안녕하세요 수강생 여러분! Architecting with Google Compute Engine 과정에 오신 것을 진심으로 환영합니다. 저는 이번 3일간 여러분과 함께 구글 클라우드 인프라 아키텍팅을 공부할 강사입니다. 본 과정은 Compute Engine을 중심으로 네트워크, 보안, 모니터링, Terraform 자동화 배포까지 실무 중심으로 습득하는 정규 과정입니다."
-->

---

<!-- Page 2 -->

## 01. 강사 소개

<div class="profile-container">
  <div class="profile-row">
    <div class="profile-period">2019 ~ 현재</div>
    <div class="profile-detail">베스핀글로벌 구글 MSP 팀 / Cloud 엔지니어</div>
  </div>
  <div class="profile-row">
    <div class="profile-period">2018 ~ 2019</div>
    <div class="profile-detail">신한 DS / 인프라 운영</div>
  </div>
  <div class="profile-row">
    <div class="profile-period">2015 ~ 2018</div>
    <div class="profile-detail">쌍용정보통신 / 네트워크 엔지니어</div>
  </div>
  <div class="profile-row">
    <div class="profile-period">2015 년</div>
    <div class="profile-detail">연세 IT 전문학원</div>
  </div>
  <div class="profile-row">
    <div class="profile-period">2012 년</div>
    <div class="profile-detail">충북대학교 고고미술사학과 (졸업)</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"본격적인 수업에 앞서 제 소개를 간단히 드리겠습니다. 저는 네트워크 엔지니어를 시작으로 금융권 인프라 운영을 거쳐, 2019년부터 지금까지 베스핀글로벌 구글 MSP 팀에서 Google Cloud 엔지니어 및 아키텍트로 재직하고 있습니다. 현업에서 수많은 기업의 Google Cloud 마이그레이션과 아키텍팅 솔루션을 직접 구축하며 얻은 실무 팁과 노하우를 공유해 드리겠습니다."
-->

---

<!-- Page 3 -->

## 에티켓 (Etiquette - Part 1)

<div class="card-grid-3">
  <div class="card" style="text-align: center;">
    <div style="font-size: 40px; margin-bottom: 10px;">📵</div>
    <div class="card-title">통화 금지</div>
    <div class="card-desc">강의 진행 중 휴대폰 통화는 강의실 밖에서 진행해 주세요.</div>
  </div>
  <div class="card" style="text-align: center;">
    <div style="font-size: 40px; margin-bottom: 10px;">🚫</div>
    <div class="card-title">녹화 금지</div>
    <div class="card-desc">저작권 보호를 위해 강의 내용의 캡처 및 화면 녹화를 금지합니다.</div>
  </div>
  <div class="card" style="text-align: center;">
    <div style="font-size: 40px; margin-bottom: 10px;">❓</div>
    <div class="card-title">질문하기</div>
    <div class="card-desc">궁금한 사항은 손을 들거나 채팅창을 통해 언제든 질문해 주세요.</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"원활한 강의 환경을 위한 첫 번째 에티켓입니다. 급한 통화는 강의실 밖에서 진행해 주시기 바라며, 자료 저작권 보호를 위해 화면 캡처나 녹화를 금지하고 있습니다. 궁금한 점이 생기시면 언제든 편하게 질문해 주세요."
-->

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

---

<!-- Page 5 -->

## Google Cloud 생태계 (Global Ecosystem)

<div class="card-grid-3" style="margin-top:20px;">
  <div class="card">
    <div class="card-title">🌐 글로벌 인프라</div>
    <div class="card-desc">Search, YouTube, Gmail 지원 초고속 Google 글로벌 사설 망</div>
  </div>
  <div class="card">
    <div class="card-title">⚡ 오픈소스 생태계</div>
    <div class="card-desc">Kubernetes, Terraform, Redis, MongoDB 완벽 호환</div>
  </div>
  <div class="card">
    <div class="card-title">🤖 AI & Analytics</div>
    <div class="card-desc">Vertex AI, Gemini, BigQuery 빅데이터 최첨단 연계</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"Google Cloud는 수십억 명의 사용자를 매일 처리하는 YouTube, Gmail, Search와 동일한 전용 사설 광케이블 백본망 위에서 구동됩니다. 쿠버네티스나 테라폼 같은 오픈소스 생태계를 이끌며 최신 AI인 Gemini까지 완벽히 연결됩니다."
-->

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

---

<!-- Page 7 -->

## Google Cloud는...

<div class="card" style="margin-top: 30px; padding: 40px; text-align: center;">
  <h2 style="color: #1a73e8; margin-bottom: 20px;">다양한 비즈니스 요구사항을 충족하는 클라우드</h2>
  <p style="font-size: 22px; color: #3c4043;">컴퓨팅, 데이터베이스, AI, 네트워킹에 이르기까지 기업의 상황에 맞는 최적의 클라우드 인프라 제품군을 다각도로 제공합니다.</p>
</div>

<!--
comment:
💬 [강사 대본]
"Google Cloud는 기업마다 다른 비즈니스 상황과 요구사항을 맞춤형으로 충족할 수 있도록 정교한 제품군을 갖추고 있습니다. 자유롭게 조합할 수 있는 유연성이 가장 큰 장점입니다."
-->

---

<!-- Page 8 -->

## 일반적인 문제에 대한 솔루션 다양성

<div class="card" style="margin-top: 20px; padding: 30px; border-left: 6px solid #1a73e8;">
  <h3 style="color: #1a73e8; font-size: 28px; margin-top:0;">💡 하나의 과제에 대해 2개 이상의 솔루션 제공</h3>
  <p style="font-size: 21px; color: #3c4043; line-height: 1.6;">
    Google Cloud는 동일한 목적의 워크로드에 대해서도 <strong>가상 머신(IaaS), 컨테이너(CaaS), 서버리스(PaaS)</strong> 등 조직의 관리 역량과 비용 모델에 따라 선택할 수 있는 다중 솔루션을 제공합니다.
  </p>
</div>

<!--
comment:
💬 [강사 대본]
"GCP 아키텍팅의 핵심 원칙은 '하나의 문제에 항상 2개 이상의 솔루션이 존재한다'는 점입니다. VM, 컨테이너, 서버리스 중 조직의 역량과 비용 모델에 맞는 최적의 기술을 선택하시면 됩니다."
-->

---

<!-- Page 9 -->

## 솔루션 연속성 (Solution Continuum)

| 구분 | IaaS (Compute Engine) | CaaS (GKE) | PaaS / Serverless (Cloud Run) |
| :--- | :--- | :--- | :--- |
| **제어 수준** | OS / Kernel 전체 제어 | Container 오케스트레이션 | 애플리케이션 코드 & 이미지 |
| **운영 모델** | SysOps (직접 OS 관리) | DevOps (클러스터 관리) | No-Ops (Google 완전 관리) |
| **적용 영역** | 커스텀 OS, 레거시 이전 | 마이크로서비스 (K8s) | Web API, 이벤트를 받는 웹 앱 |

<!--
comment:
💬 [강사 대본]
"IaaS(Compute Engine)는 OS 전체 제어가 가능하지만 직접 관리(SysOps) 부담이 큽니다. 반면 서버리스(Cloud Run)는 구글이 인프라를 완전 관리해주는 No-Ops 환경을 제공합니다."
-->

---

<!-- Page 10 -->

## 인프라, 사용자, 애플리케이션 구조

<div class="card-grid-3" style="margin-top:20px;">
  <div class="card">
    <div class="card-title">🏗️ 기반 인프라</div>
    <div class="card-desc">Google 글로벌 전용 사설망, Compute Engine VM, VPC 네트워크</div>
  </div>
  <div class="card">
    <div class="card-title">📦 애플리케이션 계층</div>
    <div class="card-desc">GKE Pod, Cloud Run 컨테이너, 서버리스 함수 워크로드</div>
  </div>
  <div class="card">
    <div class="card-title">🔐 사용자 및 보안</div>
    <div class="card-desc">IAM 계정 권한 인증, Identity-Aware Proxy, 보안 게이트웨이</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"도시 구조로 비유하면 도로와 전력망 같은 도시 인프라가 바로 구글의 '기반 인프라'입니다. 상점과 차량이 '애플리케이션'이며, 시민이 '사용자'입니다. 이번 과정은 가장 밑바탕이 되는 인프라를 배웁니다."
-->

---

<!-- Page 11 -->

## 컴퓨팅 서비스 01: Compute Engine

<div class="service-hero-layout">
  <div>
    <ul>
      <li><strong>Google Cloud의 대표 IaaS (Virtual Machines)</strong></li>
      <li><strong>자유로운 인프라 스펙 설정</strong>: vCPU 및 메모리 커스텀 사양 구성</li>
      <li><strong>Google 고유 기술</strong>: Live Migration (물리 점검 시 무중단 이동)</li>
      <li><strong>비용 절감 지원</strong>: Spot VM 최대 90% 할인 및 지속 사용 할인(SUD)</li>
    </ul>
  </div>
  <div class="service-icon-box">
    <img src="data:image/png;base64,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" alt="Compute Engine">
    <div class="service-icon-name">Compute Engine</div>
    <div style="font-size: 14px; color: #5f6368; margin-top: 6px;">Virtual Machines (IaaS)</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"대표 IaaS인 Compute Engine입니다. 구글만의 Live Migration 기능 덕분에 물리 서버 점검 시에도 수강생분의 VM이 중단되지 않고 실시간 이동됩니다."
-->

---

<!-- Page 12 -->

## 컴퓨팅 서비스 02: Google Kubernetes Engine (GKE)

<div class="service-hero-layout">
  <div>
    <ul>
      <li><strong>쿠버네티스 원조 Google의 관리형 CaaS</strong></li>
      <li><strong>대규모 컨테이너 오케스트레이션</strong>: 배포, 자동 스케일링, 복구 관리</li>
      <li><strong>운영 모드 선택</strong>:
        <ul>
          <li>GKE Standard: 클러스터 노드 직접 제어</li>
          <li>GKE Autopilot: 완전 관리형 K8s Pod 운영 (No Node Management)</li>
        </ul>
      </li>
    </ul>
  </div>
  <div class="service-icon-box">
    <img src="data:image/png;base64,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" alt="GKE">
    <div class="service-icon-name">Google Kubernetes Engine</div>
    <div style="font-size: 14px; color: #5f6368; margin-top: 6px;">Managed Container (CaaS)</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"관리형 쿠버네티스인 GKE입니다. 특히 GKE Autopilot 모드를 사용하면 노드 서버 관리 부담 없이 컨테이너 Pod 단위로만 깔끔하게 운영하실 수 있습니다."
-->

---

<!-- Page 13 -->

## 컴퓨팅 서비스 03: App Engine

<div class="service-hero-layout">
  <div>
    <ul>
      <li><strong>Google Cloud의 전통적인 PaaS (Platform-as-a-Service)</strong></li>
      <li><strong>서버 관리 제로</strong>: 개발자는 애플리케이션 소스 코드만 제출</li>
      <li><strong>자동 런타임 빌드</strong>: Python, Java, Node.js, Go 등 자동 구성</li>
      <li><strong>트래픽 기반 자동 확장</strong>: 0개부터 자동 오토스케일링</li>
    </ul>
  </div>
  <div class="service-icon-box">
    <img src="data:image/png;base64,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" alt="App Engine">
    <div class="service-icon-name">App Engine</div>
    <div style="font-size: 14px; color: #5f6368; margin-top: 6px;">Platform-as-a-Service (PaaS)</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"구글의 오리지널 PaaS인 App Engine입니다. 개발자가 소스 코드만 제출하면 구글이 알아서 인프라 구성과 트래픽 확장을 처리해 줍니다."
-->

---

<!-- Page 14 -->

## 컴퓨팅 서비스 04: Cloud Functions (Cloud Run Functions)

<div class="service-hero-layout">
  <div>
    <ul>
      <li><strong>이벤트 기반 FaaS (Function-as-a-Service)</strong></li>
      <li><strong>이벤트 반응형 트리거</strong>:
        <ul>
          <li>Cloud Storage 파일 업로드 감지 및 자동 처리</li>
          <li>Cloud Pub/Sub 메시지 수신 시 1초 단위 스크립트 실행</li>
        </ul>
      </li>
      <li><strong>극강의 비용 효율</strong>: 미사용 시 트래픽 0일 때 비용 0원</li>
    </ul>
  </div>
  <div class="service-icon-box">
    <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAgAAAAIACAYAAAD0eNT6AAAh8klEQVR42u3dfaxkZ13AcRSMEQUREIkQ40uikBgURUAUxLbaNxtDC+W13d3SbYFSobxDsW/YZbtd+gp1ty8korzkemdmyxIEtFShbLtnZltRQQ0xMSRgQvuHlju795zZ9njO7J272+2+3Dv3zMx5zvP5JE9CoGzvnjlzft9z5py5T3gCAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABQE3Nz+RNtBYjTFXn+o+WyJSAyO3v5k9tJdlc7GbzH1oD4hn+rm91erjzPf8QWgdiGfzfLh0sEQHTD/+D7P7tNBECMw39ptXqDd9s6ENnwFwEQ9/BfXr3Bu2wliGz4iwCIfPgfXJfYWhDZ8F8+CchuFQEQ5/A/8HFAN3unrQaRDX8RAHEP/9HqJNk7bD2IbPgfPAnYLgIgwuF/yJnAn9mKENfwFwEQ+/Bffjogu9jWhLiGvwiAyIf/0nq0083ebqtCXMP/kLVNBEB8w385Aop1ka0L0Q1/EQARD38RAHEP/9H6SxEA8Q3/5QhoJdnbbG2IbviLAIh4+B+8J6CXvdVWh+iG/4EbA5PsFhEA8Q3/gx8H9LK32PoQ1/AXARD38D/4cUA3u9CrAHEN/+UvC+tlnxABEN/wP/QRwQu8GhDX8BcBEPfwH61HRADEN/wPWR/3qkB8w385AoqfaaNXB6Ib/iIAIh7+yxHQ6mXne5UguuEvAiDi4X/oxwFv9mpBdMNfBEDEw//gxwHd7DyvGkQ3/Ee/QOhmrxrEN/wPvSdgg1cP4hr+IgDiHv4HPw5IsvVeRYhr+C8/ItjNbvIqQnzDXwRAxMNfBEDcw//gxwG9bJ1XFeIa/ssryW70qkJ8w3+09hfrXK8uRDb8RQBEPfyXI6A4sJ3jVYbIhr8IgKiH/3IEdJL0TV5tiGz4j1Yvu8GrDfENfxEAMQ9/EQBRD/+D9wQk6Ru9+hj+kQ3/g08HXO/Vx/CPb/gfvCegl77BXoDhH+X7XwRg+Mf65l/+OKCbvt7egOEf7brO3oDhH3EEtLvp6+wVGP4iAAz/+NaglaSvtXdg+Ee7PmbvwPAXAWD4iwAw/GOLgE6Snm1vwfCP9MbAJNtqb8HwjzgC2r30NfYaDH8RAIZ/jB8HdNNX23sw/CNdvfRaew+Gf8wfB3TTs+xFGP4iAAx/EQCGf1Qr3WJvwvCPd2XtJD3TXoXhLwLA8I8wAuZ76fPsXYSg3R2813u22tXqptfYszD8o/zO8MHl9i5CMfet/KeK/fYe710RgOFvGf6IAKuajwM227sw/A1/EAEiAAx/wx9EQDQrST9q78LwN/xBBIgAMPwNfxABIgAMf8MfRECznw7opZvsXRj+hj+IABEAhr/hDyIgoqcDrrZ3Yfgb/iACRAAY/oY/iICIIuAv7F0Y/oY/iAARAIa/4Q8iIJobA5P0I/YuDH/DH0SACADD3/AHERDNcSdJr7J3Yfgb/iACRAAY/oY/iIBoVi+90t6F4W/4gwgQAWD4G/4gAqK5MbCbXmHvwvA3/EEEiAAMf8vwBxHgOIXhb3lTgQhwvMLwt7yZQAQ0cCWDy+xdhr9l+IMIEAEY/pbhDyIgmhsDe4M/t3cZ/pbhDyJABGD4W4Y/iIBojmu9wYftXYa/ZfiDCBABGP6W4Q8iQARg+Bv+gAho+Bpcau8y/C3DH0SACMDwN/wBERDP7w4YfMjeZfgb/oAIEAEY/oY/IAKiOR4mgw/auwx/wx8QASIAw9/wB0RANKs3+IC9y/A3/AERIAIw/A1/QAREFAHvt3cZ/oY/IAJEAIa/4Q+IgIiOn++zdxn+hj8gAkQAhr/hD4iAiL42+L32rgmY3zM42c5l+AMioObfGPh79i4BYPgDIiCyVc4qe5YAMPwBESAAEACGPyACBAACwPAHRIAAQAAY/oAIEAAIAMMfEAECAAFg+AMiQAAIAMvwB0SAABAAluEPiAABIAAswx8QAQJAABj+ACJAAAgAwx9ABAgAAWD4A4gAASAADH8AESAABIDhDyACBIAAMPwBRIAAEACGPyACRIAAEACGPyACBIAAEACGPyACBAACwPAHRIAAQACsfl02v9i3FwB1j4Dtd6WZAEAAVLQ+8Ll9+WlbFh60FwB196fXLTz0ib9fFAAIgCqG/wlXLwgAIAjlserka/p5rBEgAARApcNfAAAhBUB5zIo1AgSAAKh0+AsAILQAiDUCBIAAqHT4CwAgxACIMQIEgACodPgLACDUAIgtAgSAAKh0+AsAIOQAiCkCBIAAqHT4CwAg9ACIJQIEgACodPgLAKAJARBDBAgAAVDp8BcAQFMCoOkRIAAEQKXDXwAATQqAJkeAABAAlQ5/AQA0LQCaGgECQABUOvwFANDEAGhiBAgAAVDp8BcAQFMDoGkRIAAEQKXDXwAATQ6AJkWAABAAlQ5/AQA0PQCaEgECQABUOvwFABBDADQhAgSAAKh0+AsAIJYACD0CBIAAqHT4CwAgpgAIOQIEgACodPgLACC2AAg1AgRA5AFQ9fAv1+lb+9+3FwB1d/qWhR9UeewLLQIEQMQBUPXwP7FYZ93Qzzfese/L9gKg7jbcuu+rZ2yt9gQopAgQAJEGQNXD/5RrFvJ12/bmF9xRrn1/Zy8A6q48VpXHrNd/vJ//0ab4IkAARBgAVQ7/0Vn/BbePhr8AAMIKgHKdd9vevMqrASFEgACILACqHP6nFmf95247dPALACDMABitKq8G1D0CBEBEAVDV8D/yWb8AAMIPgKqvBtQ5AgRAJAFQ1fA/ZctCvm770Qa/AADCD4DlqwGfqOZqQF0jQABEEABVDP/hWf+NxzrrFwBAswKgXG++bW/+J1ubGQECoOEBUMXwf+wd/gIAiCcARut1FdwbULcIEAAT8Kld6WuaMPzLs/5X31g+17+a4S8AgOYFQFVXA+oUAQJgAq77Svqh0Id/eYf/8T/rFwBAPAFw6L0BJ300/Ai47suDD9gLGhYAaxn+o8/6N94x7vAXAECzA2B0NWAtTwrUIQLKWWUvaFAArGX4n7plLWf9AgCIJwCquBow6wgQAA0KgHGH//if9QsAIO4AGH5vwK3jXw2YZQQIgIYEwLjD/9RV3+EvAAABcMSrAR8f72rArCJAADQgAMYZ/uVZ/2sqPesXAEDcAbCWqwGziAABEHgAjDP813aHvwAABMBKvjdgtVcDph0BAiDgAFj18N9U9Wf9AgAQAFVeDZhmBAiAQANgtcO/vMN//fZJD34BAAiAI14N2FS/CBAAAQbAqob/pkl+1i8AAAGwoqsBq/wWwWlEgAAILABWM/zLz/rXb5vm4BcAgACo6mrApCNAAAQUACse/uVZ/03TPusXAIAAWPHVgGtnHwECIJAAWOnwP23LpO/wFwCAAJjm1YBJRYAACCAAVjL8h8/1z/SsXwAAAmCcJwVWcjVgEhEgAGoeACsZ/tO9w18AAAJgFlcDqo4AAVDjADje8B+d9ddn8AsAQACs6WrA1ulFgACoaQAcb/ifNjzrr+PwFwCAAFjT1YCb9+YnfbQ/8QgQADUMgGMN//Ks/+yb6jr4BQAgAKZxNaCKCBAANQuAYw3/8qx/w/a6D38BAAiA6u4NOPrVgLVGgACoUQAcbfifuKmun/ULAEAATOd7A6qPAAFQkwA42vCv92f9AgAQALO+GjBuBAiAGgTAkYZ/edZ/9s2hDX4BAAiAWVwNGCcCBMCMA+BIwz/Ms34BAAiAaa3XHuFJgdVGgACYYQAcPvzLL4E4+6aQB78AAATALK8GrCYCBMCMAuDw4X9a8SJuuLUJw18AAAJg6vcGbOqvOgIEwAwC4NDh35yzfgEACIBZfm/A6VtXFwECYMoBcOjwP31LP5Dn+gUAIABCuxpwvAgQAFMMgNHwP7GRZ/0CABAAtfkWwWuPHwECYEoBMBr+zfqsXwAAAqDWTwps6h81AgTAFAKgHP7lWf9rb2764BcAgACo09qwdDWgjIBbDosAATDhACiH//Csf3ssw18AAAKgjlcDTt3y2AgQABMMgEvnFhv+Wb8AAARASFcD/vT6fr7tHxYFwCQD4Kr24nBjxzf8BQAgAOq83nhLP7/1q6kAmISLP7X3zDgHvwAABEAIa2Ox/ny+f569oGIbP7lwsgAAEAC1joBiVtkLBIAAAASAAEAACABAAAgABIAAAASAAEAACABAAAgABIAAAASAAEAACABAAAgAASAAAASAABAAAgBAAAgAASAAAASAABAAAgBAAAgAASAAAASAABAAAgBAAAgAASAAAASAABAAAgBAAAgAASAAAASAABAAAgBAAAgAASAAAASAABAAAgAQAAIAASAAAAEgABAAAmAltvfyH+v0Fn+l0x28crTmu9kL27vzZ3hHjK91397n7kgGLxtt0/I/l/+dLTO+uSR/dqebvXi0TVvJ4BWde/f9ogAQAAgAAbACO3v5k9vd9HXtJLut3c2+XaxHi5UfZT3USdIvFQfb98330ud5hxxZnuc/0uoN/rDYrpuLbZYUq3+Mbdo/8M+km8v/T/n/tQWPbEcve0m7l15Z7KtfK7bZ/x1jm6btXvbPxT93Y6e7/9QyagWAAEAACIAl7T3p84sD5R2tbrZwjAPp8VY53M69++78Sd4txRnprvzpRRxdXmyT765hm363/DPKP8sWHQVqdkmx/nMN2/QHxfrYnff3f14ACAAEQLQBMLdr73OKg+FnivXIGg6oh6//6nTTs2J9n3zxO/mPt5PBZcV2eLjCbfpw+WeWf3aUMTWXP7HYBhcV68EKt+lip5td/8X78qcKAAGAAIgqAIqz/QsrHlKHrfQL7W/mz4rtsnSxXb8zqW1a/tnlvyOmbXpnd/HXir97b4L76ffnu/tPEwACAAHQ+ACY25X/xNJZfz75NfheeYNbDO+PVi+7uPg7Z1PYrln574phm3aS9Ozi7/vDKWzTR1u9dFNT7rkQAAJAAAiAxx9QH8ifVhzsvj6d4b+89u5IFs9o6vuiHBrtXnrtlLdpXv47m3yTYCfJ3lHxR1PHXcW/89NNuElQAAgAASAAHmN4A1WS3Tv1QbV01tpOBqc08X0xk+F/SAQ0cvh3s7fPbJt2s89ekec/KgAEAAKgEQEwPEtN0p0zPKiWn18vlN8h0MDL/vlMt2vDPg5o7U5fNe0z/yNcCdgqAAQAAqARAdBJBh+c9aAa3cTWlLuuh8+hl8+Yz367pk25MbDVXfzl4u/zvzXYpo+WISIABAACIOgAmN+TvqA4oA3qEADDlWS3hf5eKB/Hm+Td/mOFVeCPCB64SjX8Up+8Juuhnb38mQJAACAAggyA4UG1m91To4NquR5p7cleGvJ7Yek5/7xWq/iZgt6mvWxd3bZpEVa3CwABgAAIMgDKu+9rN6gOXAW4K9T3QfmtfJP9/oTxvywo1G8MLO+8L37+/67hNt3f3r34qwJAAAgAARBcABQHsF21DIDy7CrQqwBLX+9by21a/mxBbtMkW1/XbVqsTwoAASAABEBQAdDupr9e44NqkJdXy8fD1vjd/pNe3w3xEbZiX/hGjbdp/8578qcIAAEgAARASAGwuc4BUP4Gt9BuXDvwW/1qvU3z8mcM6uy/t/grx/mtk7NfvWydABAAAkAAhBMA5a9ANaxii6ryu+03BxVVSfa2+m/T7LMCQAAIAAEQxqDanT9j1l+msrIvXEmvCisAst0BDKvdYW3TwVwAUfU/AkAACAABEMZBNRn8QQCDKm91B51QtunSI5X9ALZrP6TfEVD8vP8Rwr4a0m+2FAACQABEHQDZxiAOqt3s26Fs07nevl8IZJvm5c8awja9++78SVP6DYprXjv2DF4uAASAABAAIVxWvTSQYfVgKNt0fnf2olACoPxZg4iq+/OfDWWbtpP0TAEgAASAAAggAEK4WW24FkPZpiE8ARDazZVL3/0fRgAE9CSAABAAAkAACAABIAAEgABAAPgIwEcAPgLwEYCPAAQAAsBNgG4CXN2wchNg5dwEKAAEgAAQAJUHgMcAq+YxwEldrfIYoAAQAAJAAFR3UPVFQJMaVr4IqPqPq3wRkAAQAAJAAFR6YPVVwBMYVr4KuGq+ClgACAABIADiG1Z+GZCo8suABIAAEAACYAIB4NcBV8yvA55QWPl1wAJAAAgAAVD5Z9a7ahsAe7KXhvg+6HQHl9f2noriZwtymybZ+hoHwCdD254CQAAIAAHwhB3J4hn1fKY6uyvU98Hcrvzpxd/h4Rpu14fLny3Ebbq9l/9Y8fP/dw236f727sVfFQACQAAIgOACYOnRtXtqdlB9JNSz/+UrK8ngsvpF1eCyoLdpL1vnYyoBIAAEgACo0Pye9AXFwWxQo7P/20J/L5Q3LxbD4Ts1GlTfCe2GyiPGapJ9rUYB8NDOXv5MASAAEADBBsCBz1gHH6zNoLovf2oT3g87etlLir9TWoPtmpY/SxO26dLvBvjfGmzTR1u701eFuh0FgAAQAALgsLOrdOeMh//CfDd7YZPeE61edvHsH/vLLm7UNi0G76y/xKqTZFtD3oYCQAAIAAHwGDt7+ZPbSXbvjA6qWTsZnNLE90W7l147u+fT02ubuE073ezts/zSnxAfpRQAAkAACIBjH1gfyJ9WHOC+PuUD6t7yaYSmvi+GV1dmEQHFvzOk7/xf/cdW2TumfSWg+Hd+unwiIfRtJwAEgAAQAEc0tyv/ieJg95npHFQH39uRDF4Ww/tj6eOAafxmu6xpl/2PHgHp2cXf94dT+cy/l25qSlAJAAEgAATAsQdWN7twss+zp18I6TeoVaG8GW+STweUf3ZTbvhbqTu7i79W/N17E9xPvz/f3X9ak7aZABAAAkAArOBqwN7nLF0NqPJS6391uulZsb5Pysfxlr4noMq4erj8M0N/1G/s/XQuf2KxDS4q1oMVbtPFTje7vilPpQgAASAABMBY2nvS5xcHxDvKO/XXcEBNinXu3XfnT/JuOfCNgUtfG7yW3x3w3fLPCPUb/qo2vJG1m11SrP9cwzb9QbE+duf9/Z9v6nYSAAJAAAiAMQ+w6evKL+spDpLfPs5vaXuok6RfKgbU++Z76fO8Q46s/Fz5wG8RHP52xjKS+sf6xTMH/pl0c/n/afJNflV83NLupVcufXnQ/x3rexKGvxo7yW7sdPef2oSb/ASAABAAAmDiyoNl+etaiyH/ytEqn+Vv786f4R0xvtZ9e59b3hw52qblfy7/O1tmDVdckvzZnW724tE2bSWDV3Tu3feLMW4LASAABIAAAASAAEAACABAAAgABIAAAASAAEAACABAAAgABIAAAASAAEAACABAAAgAASAAAASAABAAAgBAAAgAASAAAASAABAAAgBAAAgAASAAAASAABAAAgBAAAgAASAAAASAABAAAgBAAAgAASAAAASAABAAAgBAAAgAASAAAASAABAAAgAQAAIAASAAAAEgABAAAgAQAAKAFbr4U3vPFAAAAqDWAfBX/VPtBRW77ivph65qL+YbbhUAAAKgXuv82/v5RzqL+Yf/dmGDvWACAdDuZvmlc4v52Tf1BQCAAKjFOueWfv7huX15OaMuay2cYy+YUACU6wOf25efdm0/37C9LwAABMDMzvpfdf1C/v7PHhj+5br8bxfOtRdMMABGEXDipoX8tTf3BQCAAJjqetNf9vM/3vzY4S8AphQAowg44eqFA1cDbu0LAAABMJWz/nL2HD78y3Xl/MI6e8EUAuDQCCivBjT73gABAAiAWZ/1n7x5afh/7vHDXwBMOQAOjYBynb6lqfcGCABAAMzurL+/PGeONvzLdUVrYb29YIoBcHgEnNTIqwECABAAs7jDf3TWf7zhLwBmFACHR0Dz7g0QAIAAmNVZ/9E+839cAHQEwEwC4EgR0JyrAQIAEACzOOtf6fAXADMOgCNFwPBqwJaFfH3Q9wYIAEAATPusfzXDf3gT4A7fBDjTADhaBAyfFAj2ewMEACAAJnbWv/Rc/+Fz432rGP4CoCYBcLQICPdqgAAABMC0zvrHGf7DjwDa/fPsBTUIgGNFQHk14DVB3RsgAAABMI2z/nGHvwCoWQAcKwJGVwPC+N4AAQAIgEp+Ze/te4961l+u935mvOFfrqsEQL0C4HgRcOLVITwpIAAAATDJs/61Dn8BUNMAOF4E1P/eAAEACIBJnfVXMfwFQI0DYCURUF4NqOe9AQIAEADjnvWffIyz/uFn/hUM/3J9pNN/s72gpgGwkggo16nDqwECACDUAFjJWX+Vw18ABBAAK42A0dWAjQIAIKgAWMlZf9XDf/gRwI7++faCmgfASiNgdG/Auu0CAKDuAVCe9Z+5grP+qj7zFwCBBsBqIuCETbO+GiAAAAFw3LP+a2Y3/IcfAdzZ32gvCCQAVhUB5b0B1yzk67cJAIC6BMBqzvonOfwFQIABsNoIGF4NuHHaVwMEACAADl/nruKsf9LDXwAEGgCrjoCpPykgAAAB8Jiz/hv6qzpmv2fCw18ABBwA40RAeTXg1VO5GiAAAAEwzln/tIb/8CbAz/cvsBcEGgBjRcDSvQGTfVJAAABxB8BKn+uf1fAXAA0IgHEjYPi9ARO7GiAAgHgDYHjWv3mM4f/p6Q3/4UcAn+9faC8IPADGjYDlqwHbBAAgAGZ11j+L4S8AGhQAa4mA8mpAtfcGCAAgrgAY96x/VsO/XJsEQHMCYC0RMHpSoJp7AwQAEEcAjHOHfx2GvwBoYACsNQLKqwFnrflqgAAAmh8A52xb/R3+dRn+5fqLnf232AsaFgBrjYC1PykgAIDmBsD5azzrr8PwFwAT8plk/xmzfmGriIDx7w0QAEAzA2CtZ/3levffzH74l+vGv0tfZS+o2Pyewcl1eHGriIBynbLqJwUEANCsAKjirL9Ow3+4dme/YS9ocABUFQGjewMuuF0AAHEFwDjf5lf74V+sTpL9pr2g4QFQVQQMrwas6EkBAQCEHwBVnfWX612frtfwFwARBUCVETC8GnDDsa4GCAAg7ABYy3P9IQz/cs13sxfaCyIJgCojYPSkwLnbBADQnACo8qy/zsNfAEQYAFVHwJGvBggAILwAKE9oqjrrr/vwL1erl/2WvSCyAKg6Ah7/pIAAAMIJgI0Vn/WHMPwFQMQBMIkIGF0N2HjHvi/bC4AQAqA86z/lmviGvwCIPAAmEQHlOn1r//v2AqDuzrph739Uffx719+EMfyHTwHsyX7bXhBxAEwiAk7bsvCgvQCou/JYFevwFwACYCIRIACA2AIgtOE/fApgd/Yie4EAqDQCBAAQUwBcEuDwFwACYCIRIACAWAIg1OE/vAkwyX7HXiAAKo0AAQDEEAAhD38BIAAmEgECAGh6AIQ+/Ic3AXazF9sLBEClESAAgCYHwCV/Hf7wFwACYCIRIACApgZAU4Z/uXb0spfYCwRApREgAIAmBkCThr8AEAATiQABADQtAJrwmf/jbgLck73UXiAAKo0AAQA0KQCaOPwFgACYSAQIAKApAdDU4T9cuwe/ay8QAJVGgAAAmhAAjR7+AkAATCICBAAQegA0fviXNwEmg5fZCwRApREgAICQA+Cdf9384S8ABMBEIkAAAKEGQDn8W5Ecv1vdwe/ZCwRApREgAIAQAyCm4S8ABMBEIkAAAKEFQGzDf7h6g9+3FwiASiNAAAAhBUCUw18ACIBJRIAAAEIJgGiHf3kT4J7By+0FAqDSddn8Yt9eANTd+z+774etiI/VAkAATOjXTA4utycAdVUcpy5qRX6cFgACQAQA0Q3/Yj0a+zG6lQxeYW8QACIAMPwFAAJABADN00qytxn+h6xk8Af2CgEgAgDDXwAgAEQAYPhHcEx+pb1DAIgAoJE6veythr8AEAAiADD8LQEgAEQAYPhH/BRAb/CH9hQBIAKAxmj3srcY/gJAAIgAwPC3jrT2DE6wxwgAEQAY/gIAASACAMO/8cfdZHCiPUcAiAAgWK1udqHhLwAEgAgADH9rJTcBdgcn2YMEgAgADH8BgAAQAYDh3/w1+CN7kgAQAYDhLwAQACIAqKdON7vA8K/o+Nob/LE9SgCIACCU4f+I46IAEAAiADD8LQFQHzt7+ZPbSXaXHUwEAGtXHE83Gv6Vrwc/v3vfL9m7RIAIAAz/iIb//J70BfYuESACAMPf8EcEiADA8Df8EQEiAJiyVi873/A3/EWAJQLA8LcMfxFgiQAw/C3DXwRYIgAaodPN3mz4G/4iwBIBYPhbhr8IsEQAGP6W4S8CLBEAjVC8X88z/A1/EWCnFQFg+FuGvwiwRAAY/pbhLwIsEQDNGP5JtsHwN/wRASIADH/L8EcEiAAw/C3DXwSIABEAjdBJsvWGv+GPCBABYPhbhj8iQASA4W8Z/ogAEQCGv2X4IwJEABj+luEvAkSACADD3/BHBFgiAOqk3cvWGf6GPyJABEB8w3+/44nhjwgQAWD4W4Y/IkAEQCOHfzc71/A3/BEBIgAMf8vwRwSIADD8LcMfESACwPC3DH9EgAiA8LS62TmGv+GPCBABYPhbhj8iQASA4W8Z/ogAEQCN0EnSNxn+hj8iQASA4W8Z/ogAEQCGv2X4IwJEADRCO0nfaPgb/ogASwRg+FuGPyLAEgEY/pbhjwgQASKARmj10jcY/oY/IsASARj+luGPCLBEAIa/ZfgjAiwRgOFvGf6IAOsx6yJ7FyFo70mfb/gb/ogAb9xq1r/PJfmz7VkEEwHdwXu9bw1/RIA38NrWt++8L/85exQiwPAHEWD4gwgw/EEENHL1sm8Z/ogAwx9EQFzr39rfzJ9lz0EEGP4gAgx/EAGGP4iAhq5/NfwRAYY/iIDIhv/c/fnP2kMQAYY/iIB41r8Y/ogAwx9EQFzrm4Y/IsDwBxEQ2fAvtsEz7QmIAMMfREA8z/n/s+EP0UaA4Q+RRsADhj9EGwGGP0QaAQ+0d+fP8IpDlBFg+EOMEdDpZvcb/hBtBBj+EGMElMN/blf+dK8wRBkBhj9EGgF7DH+INgIMf4g0AnqGP0QbAYY/RBoBvS/8S/4zXkmIMgIMf4gxAjrdrGv4Q7QRYPhDjBFg+EPUEWD4Q6QRkHQeyJ/mFYMoI8Dwh0gjwPCHeCPA8IdII2D3XC//aa8QRBkBhj/EGAGtbnaf4Q/RRoDhDzFGgOEPUUeA4Q9RRkCS3fvF+/KneiUgyggw/CHKCDD8IeYIMPwh0gjYZfhDtBFg+EOMEdDqZt+48578KbY4RBkBhj/EGAGGP0QdAYY/RBoB98x9K/8pWxiijADDHyKNAMMf4o0Awx8ijYCvG/4QbQQY/hBlBCTZ1wx/iDYCDH+INAL+6cvfzH/SFoQoI8Dwh0gjwPCHeCPA8IdII+AfDX+INgIMf4g0Au42/CHaCDD8IdIIuLv832whiDICDH+INAK+avhDtBFg+EOUEVAswx+ijQDDH2KNAMMfoj4GPNNWAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACAuvh/U3ZJtRtSpZ0AAAAASUVORK5CYII=" alt="Cloud Functions">
    <div class="service-icon-name">Cloud Functions</div>
    <div style="font-size: 14px; color: #5f6368; margin-top: 6px;">Event-driven FaaS</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"이벤트 기반 서버리스 함수인 Cloud Functions입니다. 스토리지 파일 업로드 등 이벤트 발생 시에만 1초 간 작동하는 스크립트에 적합하며 트래픽 0일 땐 비용도 0원입니다."
-->

---

<!-- Page 15 -->

## 컴퓨팅 서비스 05: Cloud Run

<div class="service-hero-layout">
  <div>
    <ul>
      <li><strong>모던 서버리스 컨테이너 플랫폼 (Serverless Container)</strong></li>
      <li><strong>표준 Docker 컨테이너 지원</strong>: 어떤 언어/프레임워크든 완벽 작동</li>
      <li><strong>초단위 스케일링</strong>: 0개부터 수천 개까지 즉각 오토스케일링</li>
      <li><strong>호환성</strong>: Knative 기반으로 하이브리드 / 온프레미스 이전 용이</li>
    </ul>
  </div>
  <div class="service-icon-box">
    <img src="data:image/png;base64,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" alt="Cloud Run">
    <div class="service-icon-name">Cloud Run</div>
    <div style="font-size: 14px; color: #5f6368; margin-top: 6px;">Serverless Container Platform</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"가장 추천하는 모던 서버리스인 Cloud Run입니다. Docker 이미지 하나만 넣어주면 0개부터 수천 개까지 초단위로 알아서 자동 스케일링됩니다."
-->

---

<!-- Page 16 -->

## 컴퓨팅 서비스 비교 매트릭스 (Compute Options)

| 서비스 | 제어 수준 | 스케일링 속도 | 주요 유즈케이스 |
| :--- | :--- | :--- | :--- |
| **Compute Engine** | OS 포함 전체 | 분 단위 | 커스텀 OS, DB 서버, 레거시 이전 |
| **GKE** | 컨테이너 / Pod | 초~분 단위 | 대규모 마이크로서비스 |
| **App Engine** | 앱 코드 / 런타임 | 초~분 단위 | 웹 애플리케이션 (PaaS 코드 즉시 배포) |
| **Cloud Run** | 컨테이너 이미지 | 초 단위 | 웹 앱, REST API, 백엔드 서비스 |
| **Cloud Functions** | 단일 코드 함수 | 초 단위 | 이벤트 반응형 자동화 스크립트 |

<!--
comment:
💬 [강사 대본]
"5가지 컴퓨팅 옵션 비교표입니다. OS 제어는 Compute Engine, K8s 마이크로서비스는 GKE, PaaS 웹앱은 App Engine, 서버리스 컨테이너는 Cloud Run을 선택하시면 됩니다."
-->

---

<!-- Page 17 -->

## 클라우드 인프라 학습 과정

<div class="roadmap-layout">
  <div class="roadmap-info-box">
    <h3 style="color: #1a73e8; margin-top: 0; font-size: 24px;">클라우드 인프라</h3>
    <p style="font-size: 17px; color: #3c4043; line-height: 1.6;">
      Google Cloud는 전 세계 수십억 명의 사람들이 사용하는 YouTube, Gmail 등의 Google 제품을 지원하는 인프라와 동일한 글로벌 인프라에서 실행됩니다.<br><br>인프라 및 애플리케이션 구현, 배포, 마이그레이션, 유지보수에 대한 Google Cloud의 접근 방식을 알아보세요.
    </p>
  </div>
  <div class="roadmap-steps-container">
    <div class="roadmap-step-item">
      <div class="step-num">1</div>
      <div class="step-text">Google Cloud Fundamentals:<br>Core Infrastructure</div>
    </div>
    <div class="roadmap-step-item roadmap-step-active">
      <div class="step-num">2</div>
      <div class="step-text">Architecting with Google<br>Compute Engine (본 교육 과정)</div>
    </div>
    <div class="roadmap-step-item">
      <div class="step-num">3</div>
      <div class="step-text">Architecting with Google Cloud:<br>Design and Process</div>
    </div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"전체 공식 커리큘럼 로드맵입니다. 우리가 배우는 2단계 Compute Engine 과정이 인프라 아키텍팅의 가장 중심이 되는 대표 과정입니다."
-->

---

<!-- Page 18 -->

## 1일 차 주제: 기초 (Day 1 - Foundation)

<div class="card-grid-3">
  <div class="card">
    <div class="card-title">01. Google Cloud 소개</div>
    <div class="card-desc">GCP 콘솔, Cloud Shell, 프로젝트 계정 실습</div>
  </div>
  <div class="card">
    <div class="card-title">02. 가상 네트워크</div>
    <div class="card-desc">VPC 네트워킹, Private Access, Cloud NAT 실습</div>
  </div>
  <div class="card">
    <div class="card-title">03. 가상 머신</div>
    <div class="card-desc">Compute Engine VM 인스턴스 생성 및 SSH 실습</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"오늘 진행되는 1일 차 '기초' 커리큘럼입니다. 모듈 01 GCP 콘솔 및 Cloud Shell, 모듈 02 VPC 가상 네트워크, 모듈 03 Compute Engine VM 실습 순서로 진행됩니다."
-->

---

<!-- Page 19 -->

## 2일 차 주제: 핵심 서비스 (Day 2 - Core Services)

<div class="card-grid">
  <div class="card">
    <div class="card-title">04. Identity and Access Management</div>
    <div class="card-desc">IAM 사용자, 역할 및 서비스 계정 권한 실습</div>
  </div>
  <div class="card">
    <div class="card-title">05. 데이터 스토리지 서비스</div>
    <div class="card-desc">Cloud Storage 버킷 생성 및 Cloud SQL 구축 실습</div>
  </div>
  <div class="card">
    <div class="card-title">06. 리소스 관리</div>
    <div class="card-desc">BigQuery를 활용한 결제 데이터 분석 및 조직 관리 실습</div>
  </div>
  <div class="card">
    <div class="card-title">07. 리소스 모니터링</div>
    <div class="card-desc">Cloud Monitoring & Logging 시스템 모니터링 실습</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"내일 2일 차에는 IAM 권한 보안, Cloud Storage 및 Cloud SQL 데이터베이스, BigQuery 결제 분석, Cloud Monitoring 시스템 모니터링을 다룹니다."
-->

---

<!-- Page 20 -->

## 3일 차 주제: 확장 및 자동화 (Day 3 - Scaling & IaC)

<div class="card-grid">
  <div class="card">
    <div class="card-title">08. 네트워크 상호 연결</div>
    <div class="card-desc">Cloud VPN 구축 및 하이브리드 연결 실습</div>
  </div>
  <div class="card">
    <div class="card-title">09. 부하 분산 및 자동 확장</div>
    <div class="card-desc">HTTP Load Balancer & MIG Autoscaling 구축 실습</div>
  </div>
  <div class="card">
    <div class="card-title">10. 인프라 자동화</div>
    <div class="card-desc">Terraform을 활용한 코드 기반 인프라(IaC) 배포 실습</div>
  </div>
  <div class="card">
    <div class="card-title">11. 관리형 서비스</div>
    <div class="card-desc">모던 클라우드 관리형 서비스 및 아키텍처 패턴 설계</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"마지막 3일 차에는 하이브리드 Cloud VPN, 부하 분산과 자동 스케일링, 그리고 최근 필수인 Terraform 기반 인프라 코드(IaC) 자동 배포 실습을 진행합니다."
-->

---

<!-- Page 21 -->

## 실습 환경 안내 (GCP Lab Environment)

<div class="card-grid" style="margin-top:20px;">
  <div class="card">
    <div class="card-title">🏢 베스핀글로벌 실습 환경 계정</div>
    <div class="card-desc">• <strong>조직 (Organization)</strong>: `bespin.email`<br>• <strong>지정 프로젝트 (Project)</strong>: `KDT5T`</div>
  </div>
  <div class="card">
    <div class="card-title">📋 실습 진행 방법</div>
    <div class="card-desc">• 안내받은 전용 GCP 계정으로 로그인 후 `KDT5T` 프로젝트 내에서 실습 진행<br>• Qwiklabs 별도 계정 필요 없음</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"실습 환경 안내입니다. 본 실습은 퀵랩이 아니라 저희 베스핀글로벌에서 수강생분들을 위해 구성한 bespin.email 조직의 KDT5T 전용 프로젝트에서 진행됩니다."
-->

---

<!-- Page 22 -->

## 실습 보안 필수 수칙 (Security & Key Management)

<div class="alert-danger-box">
  <div class="alert-danger-title">🚨 Service Account Key & API Key 엄격 관리</div>
  <div style="font-size: 19px; color: #5c1d1a; line-height: 1.5;">
    • <strong>Service Account Key 및 API Key는 절대 Public망 또는 GitHub public 저장소에 업로드하지 마세요!</strong><br>
    • 키 노출 시 봇(Bot)에 의한 <strong>해킹 탐지 및 과도한 서비스 금액 폭탄(비용 발생)</strong>이 유발됩니다.
  </div>
</div>

<ul>
  <li><strong>보안 관리 수칙</strong>: `.gitignore` 파일 자격 증명 키(`*.json`, `.env`) 필수 등록</li>
</ul>

<!--
comment:
🚨 [보안 강조 강사 대본]
"가장 중요한 보안 수칙입니다! Service Account Key JSON 파일이나 API Key는 절대로 GitHub 등 공개 저장소에 올리시면 안 됩니다. 노출 시 봇에 의해 해킹당하고 수천만 원의 비용 폭탄이 청구됩니다. 반드시 .gitignore에 등록해 관리하세요!"
-->

---

<!-- Page 23 -->

## 실습 비용 및 리소스 관리 수칙 (FinOps Guide)

<div class="alert-warning-box">
  <div class="alert-warning-title">⚠️ 실습 종료 시 VM Off 및 비용 인지 수칙</div>
  <div style="font-size: 19px; color: #5c3c00; line-height: 1.5;">
    • <strong>수업 종료 및 실습 미진행 시에는 항상 가상 머신(VM)을 끄기(OFF)해야 합니다.</strong><br>
    • GCP 결제 데이터는 <strong>최소 2일 후에나 확인 가능</strong>하므로, 실습 진행 시 항시 비용 발생 위험을 고려해야 합니다.
  </div>
</div>

<ul>
  <li><strong>리소스 절감 체크리스트</strong>: 미사용 Compute Engine VM, External IP 즉시 정리</li>
</ul>

<!--
comment:
⚠️ [비용 관리 강사 대본]
"수업 종료 시나 쉬는 시간엔 반드시 켜둔 Compute Engine VM을 OFF로 끄셔야 합니다. GCP 결제 데이터는 최소 48시간(2일) 뒤에 집계되므로 '지금 비용 안 떴네' 하고 방치하시면 2일 뒤에 큰 금액이 찍힙니다."
-->

---

<!-- Page 24 -->

## 실습 환경 기본 유의사항 종합 (Lab Guidelines)

<div class="card-grid">
  <div class="card">
    <div class="card-title">🔒 자격 증명 보안</div>
    <div class="card-desc">Service Account / API Key 공유 금지 및 GitHub 퍼블릭 업로드 절대 엄금</div>
  </div>
  <div class="card">
    <div class="card-title">🛑 리소스 전원 관리</div>
    <div class="card-desc">실습 중단 및 일과 종료 시 VM 인스턴스 OFF 필수 이행</div>
  </div>
  <div class="card">
    <div class="card-title">💰 결제 시차 인지</div>
    <div class="card-desc">요금 집계는 최소 2일(48시간) 후 반영되므로 사전 비용 고려 필수</div>
  </div>
  <div class="card">
    <div class="card-title">🏢 지정 프로젝트 사용</div>
    <div class="card-desc">`bespin.email` 조직의 `KDT5T` 프로젝트 전용 실습 이행</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"앞서 말씀드린 보안, VM 전원 관리, 2일 요금 시차 인지, KDT5T 지정 프로젝트 사용 등 4가지 유의사항 종합 정리 카드입니다."
-->

---

<!-- Page 25 -->

## 수업 종료 후 수료 및 복습 안내

<ul>
  <li><strong>강의 자료 및 프로젝트 활용</strong>: 제공된 실습 가이드 및 `KDT5T` 프로젝트 내 결과물 복습</li>
  <li><strong>문의 및 지원</strong>: 교육 수료 후 기술 관련 문의는 담당 강사 및 MSP 팀 채널 활용</li>
</ul>

<!--
comment:
💬 [강사 대본]
"수업 수료 후에도 제공해 드린 교재와 프로젝트 자료로 복습하실 수 있으며, 문의 사항은 MSP 팀 기술 지원 채널로 질문해 주시면 친절히 가이드해 드리겠습니다."
-->

---

<!-- Page 26 -->

<!-- _class: lead -->

<div class="cover-header-logo">
  <img src="https://www.gstatic.com/images/branding/product/2x/google_cloud_64dp.png" width="48" style="box-shadow:none; border-radius:0; border:none;">
  <span class="cover-header-text">Google Cloud</span>
</div>

<div class="badge badge-cover">Q & A SESSION</div>

# 감사합니다!

### 질문이나 궁금하신 점이 있으시면 편하게 말씀해 주세요.

<div class="cover-footer-info">
  Google Cloud 교육 자료 | 베스핀글로벌 2026 개정판
</div>

<!--
comment:
💬 [강사 대본]
"이상으로 오리엔테이션 및 모듈 00 소개를 마치겠습니다. 궁금하신 점이 있으시면 편하게 질문해 주시고, 없으시면 10분 휴식 후 모듈 01 본격 수업으로 들어가겠습니다. 감사합니다!"
-->
