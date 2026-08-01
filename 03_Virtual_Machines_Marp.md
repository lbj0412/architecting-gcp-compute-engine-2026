---
marp: true
theme: uncover
paginate: true
header: ''
footer: ''
style: |
  @import url("https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.css");
  
  * {
    animation: none !important;
    transition: none !important;
  }
  section *, section ul, section li, section div, section p {
    opacity: 1 !important;
    visibility: visible !important;
  }

  section {
    font-family: "Pretendard Variable", Pretendard, -apple-system, BlinkMacSystemFont, system-ui, Roboto, "Helvetica Neue", "Segoe UI", "Apple SD Gothic Neo", "Noto Sans KR", "Malgun Gothic", "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    background: #f8f9fa;
    color: #202124;
    padding: 55px 65px 35px 65px;
    font-size: 20px;
    line-height: 1.45;
    letter-spacing: -0.02em;
    box-sizing: border-box;
  }
  
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

  section:not(.lead):not(.section-divider) p,
  section:not(.lead):not(.section-divider) ul,
  section:not(.lead):not(.section-divider) ol,
  section:not(.lead):not(.section-divider) li,
  section:not(.lead):not(.section-divider) div,
  section:not(.lead):not(.section-divider) .agenda-list-item,
  section:not(.lead):not(.section-divider) h3,
  section:not(.lead):not(.section-divider) table {
    text-align: left !important;
  }

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

  section.section-divider {
    background: #ffffff !important;
    padding: 90px 80px;
    text-align: center !important;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center !important;
    position: relative;
  }
  .section-badge {
    background: #e8f0fe;
    color: #1a73e8;
    font-size: 16px;
    font-weight: 800;
    padding: 8px 20px;
    border-radius: 20px;
    margin-bottom: 20px;
    letter-spacing: 0.05em;
  }
  .section-num-large {
    font-size: 72px;
    font-weight: 900;
    color: #1a73e8;
    line-height: 1;
    margin-bottom: 10px;
  }
  .section-title-large {
    font-size: 42px;
    font-weight: 800;
    color: #202124;
    margin-bottom: 16px;
  }
  .section-desc-box {
    font-size: 20px;
    color: #5f6368;
    font-weight: 500;
    max-width: 800px;
    line-height: 1.6;
  }

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

  h1, h2 {
    color: #1a73e8;
    font-size: 32px;
    font-weight: 800;
    margin-top: 0;
    margin-bottom: 16px;
    letter-spacing: -0.03em;
  }

  .agenda-container {
    display: flex;
    flex-direction: column;
    gap: 12px;
    margin-top: 10px;
  }
  .agenda-item {
    display: flex;
    align-items: baseline;
    gap: 16px;
    padding: 12px 18px;
    background: #ffffff;
    border-radius: 10px;
    border-left: 5px solid #1a73e8;
    box-shadow: 0 2px 8px rgba(60, 64, 67, 0.05);
  }
  .agenda-num {
    font-size: 20px;
    font-weight: 800;
    color: #1a73e8;
    min-width: 32px;
  }
  .agenda-title {
    font-size: 20px;
    font-weight: 700;
    color: #202124;
    min-width: 340px;
  }
  .agenda-desc {
    font-size: 16px;
    color: #5f6368;
    font-weight: 400;
  }

  table.comp-table {
    width: 100%;
    border-collapse: separate;
    border-spacing: 0;
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 4px 16px rgba(0, 0, 0, 0.06);
    background: #ffffff;
    font-size: 15px;
    margin-top: 10px;
  }
  table.comp-table th {
    background: #1a73e8;
    color: #ffffff;
    font-weight: 700;
    padding: 12px 10px;
    text-align: center;
    white-space: nowrap;
  }
  table.comp-table td {
    padding: 11px 10px;
    border-bottom: 1px solid #e8eaed;
    color: #3c4043;
    vertical-align: middle;
    line-height: 1.4;
  }
  table.comp-table td.header-col {
    font-weight: 700;
    color: #1a73e8;
    background: #f8f9fa;
    white-space: nowrap;
    text-align: center !important;
  }

  ul {
    list-style: none;
    padding-left: 0;
    margin-top: 0;
  }
  li {
    position: relative;
    padding-left: 24px;
    margin-bottom: 8px;
    font-weight: 500;
    letter-spacing: -0.02em;
    font-size: 17px;
  }
  li::before {
    content: '';
    position: absolute;
    left: 4px;
    top: 9px;
    width: 6px;
    height: 6px;
    background-color: #1a73e8;
    border-radius: 50%;
  }

  /* 6번 슬라이드 원본 이미지 1:1 완벽 배치 카드 Grid */
  .features-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
    margin-top: 8px;
  }
  .feat-card {
    background: #ffffff;
    border-radius: 12px;
    padding: 14px 18px;
    box-shadow: 0 3px 12px rgba(60, 64, 67, 0.06);
    border: 1px solid #e8eaed;
  }
  .feat-card-title {
    font-size: 17px;
    font-weight: 700;
    color: #1a73e8;
    margin-bottom: 6px;
    display: flex;
    align-items: center;
    gap: 6px;
  }
  .feat-card ul {
    margin-bottom: 0;
  }
  .feat-card li {
    font-size: 15px;
    margin-bottom: 4px;
    line-height: 1.45;
  }

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
    padding: 28px;
    box-shadow: 0 6px 24px rgba(60, 64, 67, 0.08);
    border: 1px solid #e8eaed;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
  }
  .tool-icon-box img {
    max-width: 100%;
    max-height: 220px;
    object-fit: contain;
    margin-bottom: 14px;
    box-shadow: none !important;
    border-radius: 0 !important;
  }
  .tool-icon-name {
    font-size: 22px;
    font-weight: 800;
    color: #1a73e8;
  }
---
<!-- Page 1 -->
<!-- _class: lead -->

<div class="cover-header-logo">
  <img src="https://www.gstatic.com/images/branding/product/2x/google_cloud_64dp.png" width="48" style="box-shadow:none; border-radius:0; border:none;">
  <span class="cover-header-text">Google Cloud</span>
</div>

# Virtual Machines

### 2026 Modernized Edition | Module 03: Virtual Machines (Compute Engine VM)

<div class="cover-guide-box">
  Compute Engine 가상 머신(VM) 인스턴스, 2026 머신 패밀리(C3/C4/N4), 블록 스토리지, 무중단 Live Migration 및 Spot VM 종합 가이드
</div>

<div class="cover-footer-info">
  Google Cloud 교육 자료 | 베스핀글로벌 2026 개정판
</div>

<!--
comment:
💬 [강사 대본]
"안녕하세요 수강생 여러분! 모듈 03에서는 Google Cloud의 대표 IaaS 서비스인 Compute Engine 가상 머신(VM)에 대해 배웁니다. VM의 핵심 개념부터 2026 최신 머신 시리즈, 스토리지 옵션, 무중단 라이브 마이그레이션 및 비용 최적화 방안까지 자세히 알아보겠습니다."
-->

---

<!-- Page 2 -->

## 모듈 03 학습 목차 (Agenda)

<div class="agenda-container">
  <div class="agenda-item">
    <span class="agenda-num">01</span>
    <span class="agenda-title">Compute Engine 옵션 & 머신 시리즈</span>
    <span class="agenda-desc">| VM 개념 및 2026 최신 C3/C4/N4/A3 머신 타입 사양</span>
  </div>
  <div class="agenda-item">
    <span class="agenda-num">02</span>
    <span class="agenda-title">가상 머신 접근 및 수명주기</span>
    <span class="agenda-desc">| SSH/RDP 접속, IAM 역할 제어 및 인스턴스 생애주기</span>
  </div>
  <div class="agenda-item">
    <span class="agenda-num">03</span>
    <span class="agenda-title">Compute Engine 스토리지 옵션</span>
    <span class="agenda-desc">| Persistent Disk, Hyperdisk, Local SSD, Cloud Storage</span>
  </div>
  <div class="agenda-item">
    <span class="agenda-num">04</span>
    <span class="agenda-title">무중단 실시간 이동 (Live Migration)</span>
    <span class="agenda-desc">| 물리 서버 점검 시 무중단 VM 자동 실시간 이동 프로세스</span>
  </div>
  <div class="agenda-item">
    <span class="agenda-num">05</span>
    <span class="agenda-title">Spot VM & 할인 요금제 (Cost FinOps)</span>
    <span class="agenda-desc">| Spot VM (최대 90% 할인), 지속 할인(SUD) 및 약정 할인(CUD)</span>
  </div>
  <div class="agenda-item">
    <span class="agenda-num">06</span>
    <span class="agenda-title">가상 머신 구축 및 실습</span>
    <span class="agenda-desc">| Compute Engine VM 생성, 커스텀 사양 구성 및 SSH 접속 실습</span>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"모듈 03의 학습 목차입니다. VM 옵션부터 액세스 관리, 스토리지, 라이브 마이그레이션, Spot VM 요금 모델, 그리고 실제 VM 생성 실습 순서로 진행됩니다."
-->

---

<!-- Page 3 -->
<!-- _class: section-divider -->

<div class="section-badge">SECTION 01</div>
<div class="section-num-large">01</div>
<div class="section-title-large">Compute Engine 옵션 & 머신 시리즈</div>
<div class="section-desc-box">
  Google Cloud Compute Engine 가상 머신의 핵심 개념과 2026 최신 머신 패밀리(범용, 컴퓨팅, 메모리, GPU 가속기) 분류 및 커스텀 사양 구성 가이드
</div>

<!--
comment:
💬 [강사 대본]
"첫 번째 단원인 Compute Engine 옵션 및 머신 시리즈입니다. VM의 기본 개념과 2026 최신 머신 패밀리에 대해 다루겠습니다."
-->

---

<!-- Page 4 -->

## Google Cloud 컴퓨팅 및 처리 옵션 비교 (Compute Options)

<table class="comp-table">
  <thead>
    <tr>
      <th style="width: 14%;">구분</th>
      <th style="width: 18%;">Compute Engine</th>
      <th style="width: 17%;">GKE</th>
      <th style="width: 17%;">App Engine</th>
      <th style="width: 17%;">Cloud Functions</th>
      <th style="width: 17%;">Cloud Run</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="header-col">언어 지원</td>
      <td>모든 OS 및 언어</td>
      <td>모든 컨테이너</td>
      <td>Python, Java, Go, Node.js 등</td>
      <td>Node.js, Python, Go 등</td>
      <td>모든 컨테이너 (Docker)</td>
    </tr>
    <tr>
      <td class="header-col">사용 모델</td>
      <td><strong>IaaS</strong> (가상 머신)</td>
      <td><strong>IaaS / PaaS</strong></td>
      <td><strong>PaaS</strong> (웹 앱)</td>
      <td><strong>Serverless FaaS</strong></td>
      <td><strong>Serverless PaaS</strong></td>
    </tr>
    <tr>
      <td class="header-col">확장 방식</td>
      <td>MIG 자동 확장</td>
      <td>Pod / Node 확장</td>
      <td>관리형 자동 확장</td>
      <td>이벤트 0➔N 확장</td>
      <td>HTTP 0➔N 확장</td>
    </tr>
    <tr>
      <td class="header-col">주요 사례</td>
      <td>일반 OS 워크로드</td>
      <td>컨테이너 클러스터</td>
      <td>확장형 웹 애플리케이션</td>
      <td>이벤트 기반 백엔드</td>
      <td>컨테이너화 앱 서버리스 배포</td>
    </tr>
  </tbody>
</table>

<!--
comment:
💬 [강사 대본]
"원본 교안 4번 장표의 6대 컴퓨팅 처리 옵션 비교표입니다. Compute Engine, GKE, App Engine, Cloud Functions, Cloud Run까지 언어 지원 및 사용 모델을 한눈에 비교할 수 있습니다."
-->

---

<!-- Page 5 -->

## Compute Engine: Infrastructure as a Service (IaaS)

<div class="tool-hero-layout">
  <div>
    <ul>
      <li><strong>사전 정의된 머신 유형 및 커스텀 머신 유형</strong>:
        <ul>
          <li>요구사항에 맞는 vCPU(코어) 및 메모리(RAM) 맞춤 조립</li>
        </ul>
      </li>
      <li><strong>유연한 독립 스토리지 옵션 (2026 Modernized)</strong>:
        <ul>
          <li><strong>영구 디스크 (Persistent Disk)</strong>: Standard, <strong>Balanced PD (균형 성능)</strong>, SSD, Extreme PD</li>
          <li><strong>차세대 Hyperdisk</strong>: IOPS 및 스루풋 독립 동적 제어</li>
          <li><strong>Local SSD</strong>: 물리 서버 직접 탑재 초고속 NVMe 캐시</li>
          <li><strong>Cloud Storage</strong>: 대용량 오브젝트 스토리지 버킷 연동</li>
        </ul>
      </li>
      <li><strong>글로벌 네트워킹 & OS 지원</strong>: Linux 및 Windows Server 지원</li>
    </ul>
  </div>
  <div class="tool-icon-box">
    <img src="data:image/png;base64,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" alt="Compute Engine IaaS">
    <div class="tool-icon-name">IaaS Architecture</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"5번 장표에서는 Compute Engine IaaS 구조를 설명합니다. vCPU/RAM 설정, Standard/Balanced PD/SSD/Hyperdisk 등 다양한 디스크 옵션과 글로벌 네트워킹을 유연하게 결합할 수 있습니다."
-->

---

<!-- Page 6 -->

## Compute Engine의 특징 (Features of Compute Engine)

<div class="features-grid">
  <div class="feat-card">
    <div class="feat-card-title">⚙️ 머신 크기를 알맞게 조정</div>
    <ul>
      <li>추천 엔진을 통한 최적의 머신 크기</li>
      <li>Cloud Monitoring 통계 기반 분석</li>
      <li>VM 생성 또는 크기 조정 후 24시간 뒤에 새로운 추천 제공</li>
    </ul>
  </div>
  
  <div class="feat-card">
    <div class="feat-card-title">🌐 전역 부하 분산</div>
    <ul>
      <li>고가용성을 위한 멀티 리전 전역 부하 분산 연동</li>
    </ul>
  </div>

  <div class="feat-card">
    <div class="feat-card-title">🛡️ OS 패치 관리</div>
    <ul>
      <li>패치 승인 만들기</li>
      <li>유연한 예약 설정</li>
      <li>고급 패치 구성 설정 적용</li>
    </ul>
  </div>

  <div class="feat-card">
    <div class="feat-card-title">🔌 인스턴스 자동화 & 메타데이터</div>
    <ul>
      <li>인스턴스 메타데이터 활용</li>
      <li>시작 및 종료 스크립트 자동 실행</li>
    </ul>
  </div>

  <div class="feat-card">
    <div class="feat-card-title">🛡️ 가용성 정책 (Availability)</div>
    <ul>
      <li><strong>라이브 마이그레이션 (Live Migration)</strong></li>
      <li><strong>자동 다시 시작 (Automatic Restart)</strong></li>
    </ul>
  </div>

  <div class="feat-card">
    <div class="feat-card-title">💰 유연한 비용 모델</div>
    <ul>
      <li>초당 청구 (Per-second Billing)</li>
      <li>지속 사용 할인 (SUD)</li>
      <li>약정 사용 할인 (CUD)</li>
    </ul>
  </div>

  <div class="feat-card" style="grid-column: span 2; background: #e8f0fe; border-color: #1a73e8;">
    <div class="feat-card-title" style="color: #1a73e8;">⚡ 선점형 VM 및 스팟 VM (Spot VMs)</div>
    <ul style="display: flex; gap: 30px;">
      <li>최대 91% 비용 할인 혜택</li>
      <li>SLA 없음 (배치 워크로드 및 백그라운드 처리 적합)</li>
    </ul>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"원본 교안 6번 장표의 Compute Engine 전체 특징입니다. 머신 크기 알맞게 조정, 인스턴스 메타데이터/스크립트, 라이브 마이그레이션 및 자동 다시 시작 가용성 정책, 전역 부하 분산, OS 패치 관리, 초당 청구/SUD/CUD, 그리고 최대 91% 할인되는 선점형/스팟 VM까지 원본의 모든 항목을 가이드합니다."
-->

---

<!-- Page 7 -->

## 범용 워크로드용 머신 타입 (General-Purpose: E2, N1, N2, N4)

<div class="card-grid">
  <div class="card">
    <div class="card-title">🌱 E2 시리즈 (Cost-Optimized)</div>
    <div class="card-desc">비용 최적화형 인스턴스, 소규모 웹 서버 및 개발/테스트 환경에 적합 (최대 32 vCPU)</div>
  </div>
  <div class="card">
    <div class="card-title">⚡ N2 / N4 시리즈 (2026 Latest Standard)</div>
    <div class="card-desc">최신 4세대 인텔/AMD 프로세서 기반, 비즈니스 핵심 애플리케이션 및 웹 서비스용 균형 사양</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"범용 머신 타입인 E2 및 N4 시리즈입니다. CPU와 메모리 비율이 균형을 이루어 일반적인 웹 서버나 개발 서버 구축 시 가장 많이 활용됩니다."
-->

---

<!-- Page 8 -->

## 컴퓨팅 최적화 머신 타입 (Compute-Optimized: C2, C3, C4)

<div class="card" style="margin-top: 15px; padding: 24px; border-left: 6px solid #1a73e8;">
  <h3 style="color: #1a73e8; font-size: 22px; margin-top:0;">🚀 초고성능 CPU 연산 워크로드 전용 (C3 & C4 Series)</h3>
  <p style="font-size: 19px; color: #3c4043; line-height: 1.6;">
    • <strong>최고 주파수 프로세서 탑재</strong>: 코어당 최상의 성능과 빠른 클럭 속도 제공<br>
    • <strong>주요 추천 워크로드</strong>: 고성능 게임 서버, 전자 설계 자동화(EDA), 과학 계산 HPC, 실시간 인코딩<br>
    • <strong>2026 C4 시리즈</strong>: Google Custom Titanium SmartNIC 연동으로 네트워크 지연 시간 대폭 단축
  </p>
</div>

<!--
comment:
💬 [강사 대본]
"컴퓨팅 최적화 머신 타입인 C3 및 C4 시리즈입니다. 코어당 연산 속도가 극대화되어 연산 집약적인 게임 서버나 HPC 워크로드에 최적화되어 있습니다."
-->

---

<!-- Page 9 -->

## 메모리 최적화 머신 타입 (Memory-Optimized: M2, M3)

<div class="card" style="margin-top: 15px; padding: 24px; border-left: 6px solid #34a853;">
  <h3 style="color: #34a853; font-size: 22px; margin-top:0;">🐘 대용량 인메모리 데이터베이스 전용 (Up to 12TB RAM)</h3>
  <p style="font-size: 19px; color: #3c4043; line-height: 1.6;">
    • <strong>vCPU 대비 극대화된 RAM 비율</strong>: vCPU당 최대 28GB 이상의 메모리 배치<br>
    • <strong>주요 추천 워크로드</strong>: SAP HANA 대규모 DB, 인메모리 데이터 분석, 대용량 Redis 캐시 시스템<br>
    • <strong>미션 크리티컬 보장</strong>: 다운타임 최소화를 위한 차세대 하드웨어 내결함성 탑재
  </p>
</div>

<!--
comment:
💬 [강사 대본]
"메모리 최적화 머신 타입인 M3 시리즈입니다. 최대 12TB 메모리를 제공하여 SAP HANA나 대규모 인메모리 데이터베이스 운영에 필수적입니다."
-->

---

<!-- Page 10 -->

## 가속기 최적화 머신 타입 (Accelerator-Optimized: A2, A3)

<div class="card" style="margin-top: 15px; padding: 24px; border-left: 6px solid #ea4335;">
  <h3 style="color: #ea4335; font-size: 22px; margin-top:0;">🤖 생성형 AI & 딥러닝 훈련 전용 (NVIDIA H100 & A100 GPU)</h3>
  <p style="font-size: 19px; color: #3c4043; line-height: 1.6;">
    • <strong>NVIDIA H100 Tensor Core GPU 장착 (A3 시리즈)</strong>: 초대형 언어 모델(LLM) 훈련 및 추론속도 극대화<br>
    • <strong>초고속 GPU 간 패브릭 통신</strong>: NVSwitch 기술로 GPU 간 3.6TB/s 상호 연결 대역폭 제공<br>
    • <strong>Gemini AI 인프라 기반</strong>: AI/ML 파이프라인 전용 맞춤 클러스터링 구성
  </p>
</div>

<!--
comment:
💬 [강사 대본]
"가속기 최적화 A3 시리즈입니다. NVIDIA H100 GPU가 탑재되어 LLM 생성형 AI 모델 훈련과 딥러닝 워크로드를 초고속으로 수행합니다."
-->