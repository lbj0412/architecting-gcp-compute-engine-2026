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
    padding: 60px 70px 40px 70px;
    font-size: 21px;
    line-height: 1.5;
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
    font-size: 33px;
    font-weight: 800;
    margin-top: 0;
    margin-bottom: 18px;
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
    padding-left: 26px;
    margin-bottom: 10px;
    font-weight: 500;
    letter-spacing: -0.02em;
    font-size: 19px;
  }
  li::before {
    content: '';
    position: absolute;
    left: 4px;
    top: 10px;
    width: 7px;
    height: 7px;
    background-color: #1a73e8;
    border-radius: 50%;
  }

  .card-grid {
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
  }
  .card-desc {
    font-size: 16px;
    font-weight: 400;
    color: #5f6368;
    line-height: 1.5;
  }

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
    grid-template-columns: 1.1fr 0.9fr;
    gap: 20px;
    align-items: center;
    margin-top: 15px;
  }
  .tool-icon-box {
    background: #ffffff;
    border-radius: 18px;
    padding: 20px;
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
    max-height: 200px;
    object-fit: contain;
    margin-bottom: 8px;
    box-shadow: none !important;
    border-radius: 0 !important;
  }
  .tool-icon-name {
    font-size: 19px;
    font-weight: 800;
    color: #1a73e8;
  }

  .dual-img-container {
    display: flex;
    gap: 16px;
    align-items: center;
    justify-content: center;
    width: 100%;
  }
  .dual-img-card {
    display: flex;
    flex-direction: column;
    align-items: center;
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

## Compute Engine 하드웨어 연산 옵션 (CPU vs GPU)

<div class="card-grid">
  <div class="card">
    <div class="card-title">💻 CPU (중앙 처리 장치)</div>
    <div class="card-desc">
      • <strong>Central Processing Unit</strong>: 모든 일반 범용 워크로드, OS 제어 및 기본 서비스 프로세스 수행<br>
      • <strong>범용 최적화</strong>: 웹 서버, 애플리케이션 백엔드 및 일반 DB 시스템 운영에 필수
    </div>
  </div>
  <div class="card">
    <div class="card-title">🎮 GPU (그래픽 처리 장치)</div>
    <div class="card-desc">
      • <strong>Graphics Processing Unit</strong>: 대규모 수평 병렬 연산 및 딥러닝 가속<br>
      • <strong>2026 최신 GPU 지원</strong>: NVIDIA H100, A100, L40S, T4 가속기 연동 (AI/ML 및 3D 렌더링)
    </div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"원본 교안 7번 장표인 하드웨어 연산 옵션입니다. 범용 프로세스 처리를 위한 CPU와 대규모 딥러닝 병렬 연산을 가속하는 GPU의 차이점을 설명합니다."
-->

---

<!-- Page 8 -->

## Tensor Processing Unit (TPU): Google 전용 AI 가속 하드웨어

<div class="tool-hero-layout">
  <div>
    <ul>
      <li><strong>Tensor Processing Unit (TPU)</strong>: Google이 자체 설계한 AI/ML 전용 도메인 특화 하드웨어 (ASIC)</li>
      <li><strong>더 높은 에너지 효율 및 성능 제공</strong>: 대규모 행렬 연산(Matrix Multiplication) 처리에 특화</li>
      <li><strong>2026 Cloud TPU v5p & v5e 지원</strong>:
        <ul>
          <li>초대형 언어 모델 (LLM) 훈련 및 멀티모달 AI 추론 속도 극대화</li>
          <li>H100 GPU 대비 최고의 비용 대비 성능 및 클러스터 확장성 제공</li>
        </ul>
      </li>
    </ul>
  </div>
  <div class="tool-icon-box">
    <img src="data:image/png;base64,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" alt="Cloud TPU">
    <div class="tool-icon-name">Cloud TPU</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"원본 교안 8번 장표인 Cloud TPU입니다. 구글이 자체 개발한 전용 도메인 하드웨어로서 대규모 AI/ML 파이프라인과 LLM 모델 훈련 시 압도적인 효율을 자랑합니다."
-->

---

<!-- Page 9 -->

## Compute Engine 컴퓨팅 성능 및 vCPU / 메모리 구조

<div class="tool-hero-layout">
  <div>
    <ul>
      <li><strong>vCPU의 표준 정의</strong>:
        <ul>
          <li>1개의 vCPU는 물리 CPU의 <strong>1개 하드웨어 하이퍼스레드(Hyper-thread)</strong>와 1:1 대응</li>
        </ul>
      </li>
      <li><strong>vCPU 비례 네트워크 대역폭 확장</strong>:
        <ul>
          <li>네트워크 처리량은 <strong>vCPU당 2Gbps씩 비례 확장</strong> (일부 머신 예외 적용)</li>
        </ul>
      </li>
      <li><strong>유연한 메모리 (RAM) 구성</strong>:
        <ul>
          <li>vCPU 사양에 맞춘 <strong>독립적인 대용량 RAM 메모리</strong> 확장 배치</li>
        </ul>
      </li>
    </ul>
  </div>
  <div class="tool-icon-box">
    <div class="dual-img-container">
      <div class="dual-img-card">
        <img src="data:image/png;base64,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" alt="vCPU Diagram" style="max-height: 120px;">
        <span style="font-size: 13px; font-weight: 700; color: #1a73e8;">vCPU & Network</span>
      </div>
      <div class="dual-img-card">
        <img src="data:image/png;base64,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" alt="RAM Memory Icon" style="max-height: 120px;">
        <span style="font-size: 13px; font-weight: 700; color: #34a853;">RAM Memory</span>
      </div>
    </div>
    <div class="tool-icon-name" style="font-size: 17px; margin-top: 10px;">vCPU & RAM Architecture</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"원본 교안 9번 장표의 vCPU 및 메모리(RAM) 구조입니다. vCPU 1개가 1개 하이퍼스레드와 대응하며 vCPU당 2Gbps 네트워크 대역폭이 비례 확장되는 구글 아키텍처 다이어그램과 RAM 메모리 아이콘을 함께 확인하실 수 있습니다."
-->

---

<!-- Page 10 -->

## Compute Engine 디스크 스토리지 및 동적 확장

<div class="tool-hero-layout">
  <div>
    <ul>
      <li><strong>다양한 블록 스토리지 디스크 라인업</strong>:
        <ul>
          <li>표준 영구 디스크 (Standard PD)</li>
          <li>균형 영구 디스크 (Balanced PD)</li>
          <li>SSD 영구 디스크 (SSD PD / Extreme PD)</li>
          <li>초고속 로컬 SSD (Local SSD) 및 Hyperdisk</li>
        </ul>
      </li>
      <li><strong>용량 비례 성능 확장</strong>: 표준 및 SSD PD는 할당된 각 GB 공간만큼 IOPS 및 스루풋 성능이 비례하여 확장</li>
      <li><strong>무중단 동적 디스크 확장 (No Downtime)</strong>: VM 인스턴스 서비스 중단(다운타임) 없이 디스크 크기를 온라인 조절하거나 인스턴스 마이그레이션 가능</li>
    </ul>
  </div>
  <div class="tool-icon-box">
    <img src="data:image/png;base64,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" alt="Block Storage Dynamic Scaling">
    <div class="tool-icon-name">Disk Dynamic Scaling</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"원본 교안 10번 장표인 디스크 스토리지와 동적 확장입니다. Standard, Balanced, SSD, Local SSD 라인업 및 용량 비례 성능 확장 법칙, 그리고 다운타임 없는 무중단 크기 조절 이점을 설명합니다."
-->

---

<!-- Page 11 -->

## Compute Engine 강력한 네트워킹 기능 (Networking Features)

<div class="tool-hero-layout">
  <div>
    <ul>
      <li><strong>자동 및 커스텀 VPC 네트워크</strong>: 서브넷 자동 구성 및 사용자 맞춤 IP 설계</li>
      <li><strong>인바운드 / 아웃바운드 방화벽 규칙</strong>:
        <ul>
          <li>IP CIDR 대역 기반 액세스 제어</li>
          <li>인스턴스 및 그룹 네트워크 태그 기반 보안 정책 지정</li>
        </ul>
      </li>
      <li><strong>고성능 부하 분산 (Load Balancing)</strong>:
        <ul>
          <li>리전별 HTTPS 부하 분산 서비스</li>
          <li>가동 준비(Warm-up) 과정이 필요 없는 초고속 네트워크 부하 분산(NLB)</li>
        </ul>
      </li>
      <li><strong>전역 및 멀티 리전 서브네트워크</strong>: 구글 글로벌 사설 백본망 연동</li>
    </ul>
  </div>
  <div class="tool-icon-box">
    <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAgAAAAIACAMAAADDpiTIAAAAeFBMVEUAAABkm/VlnvRmmfJjnPdnnfdmnfZmnfaqxv+vy/t+rPl4qfeOt/iGsfiszfuuy/qArvmuy/tonvZDhfRBh/V6qvhgmfZChfRBhfR4qPdonPWGtPiAsPlAgPKKtPhmnPaOuvl0pvhChPRChPdlm/Zdl/Z+rPhyovas+p8/AAAAKHRSTlMAM0cUH7j/cBJAyv91lEf/zHXMuDP///9H/zGYehT//3qYcB/K/3WUF+QL1gAABTZJREFUeAHs3Ed2G0kQRdHIQJHy0rTt/tfV3re8gyttIXQKPu6d0vM/VI6QwQUAAAAAAAAAAAAAAAAAAAAAAAAAAIARl2iMqNpH1WqOqtxGVUbVPMcFmuISTfUA1vUBpnqA2yP8A+dNXKCMjhAAAkAACEAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACOAYEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAATAiJN5OKJqjKjaR9VqjqrcHuEVNM9RNX+KU5niZO5HXI37OL1SAI4ABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEIAAEAACQAAIAAEgAASAABAAAkAACABXxcaYYpEncz3LT3F7Hu6jajUWrvrvMa6KHSMWuVtH1e5j3J67UV9laQCOAASAABAAAkAACAABIAAEgAAQAAJAAFxdAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAATBF2X4di3wecQQv4qwe/xFH8OnNdTwBeLx3BNhfAPYXgP0FYH8B2F8A9heA/QVgfwHYXwD2F4D9BWB/AdhfAPYXgP0FYH8B2F8A9heA/QVgfwHYXwD2F4D9BWB/AdhfAPYXgP0FYH8B2F8A9heA/QVgfwHYXwD2F4D9BWB/AdhfAPYXgP0FYP8z3BT63X+xyLN39i96/jgWufvlGE+A/+Zl1vavWs/LbBwBnv8CsL8A7C8A+wvA/gKwvwDsLwD7C8D+ArC/AOwvAPsLwP4C6LW/AOwvAPsLwP4CsL8A7C8A+wvgxX0IoPP+f/7xUACd949oXkB23797Adl+/+YFpP17F5D2711A2r93AWn/3gWk/XsXkPbvXUDav3cBaf/eBaT9exeQ9u9dQNq/dwFp/94FpP17F5D2711A2r93AWn/YgGuit3tY5En6/PvXyzg209xVk9GLDKOEsA2lvl/nH3/ayngvzeOgNPs7xRI+/cuIO3fu4C0f+8C0v69C0j79y4g7d+7gLR/7wLS/r0LSPv3LiDt37uAtH/vAtL+vQtI+/cuIO3fu4C0f+8C0v69C0j79y4g7d+7gLR/7wLS/r0LSPv3LiDt37uAtH/vAtL+vQtI+/cuIO3fu4C0f+8C0v69C0j79y4g7d+7gLR/7wLS/r0LSPv3LiDt37uAtH/vAtL+vQtI+/cuIO3fu4C0f+8C0v69CxhRltPCqdZRNb+J2/N8RNWDsXDVP70ziGsLAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAExRNs+xyCbKVo/i9qz2UbUdJ7v/dVzgVanMbxwBCAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAAASAABIAAEACuij2a9Yiq70dU/RpVP85RlT9H1Q9RNf8WVfNNBvApyl5OUfUxqt7MUfXkK75rVG0/OgIQwC0TAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIgCku0RhxeHebqBpRNg7ymQAAAAAAAAAAAAAAAAAAAAAAAAAA8GUjG4wCAHzfhQoFTr+0AAAAAElFTkSuQmCC" alt="Compute Engine Networking">
    <div class="tool-icon-name">Network Architecture</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"원본 교안 11번 장표인 네트워킹 기능입니다. 자동/커스텀 VPC, 태그 기반 방화벽 규칙, 웜업이 필요 없는 네트워크 부하 분산 및 글로벌 사설망 연동 이점을 학습합니다."
-->

---

<!-- Page 12 -->

## 가상 머신(VM) 접속 및 액세스 방법 (Linux SSH vs Windows RDP)

<table class="comp-table">
  <thead>
    <tr>
      <th style="width: 20%;">구분</th>
      <th style="width: 40%;">Linux VM 접속 (SSH)</th>
      <th style="width: 40%;">Windows VM 접속 (RDP)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="header-col">접속 도구</td>
      <td>Google Cloud 콘솔 브라우저 SSH, Cloud Shell, gcloud SDK</td>
      <td>RDP 클라이언트 (Remote Desktop), PowerShell 터미널</td>
    </tr>
    <tr>
      <td class="header-col">키 / 인증 지정</td>
      <td>컴퓨터 또는 서드 파티 클라이언트에서 SSH 키 쌍 생성 지정</td>
      <td>Windows 관리자 암호 (Password) 초기화 설정 필수</td>
    </tr>
    <tr>
      <td class="header-col">방화벽 허용 포트</td>
      <td><strong>tcp:22 (SSH)</strong> 허용 방화벽 규칙 필요</td>
      <td><strong>tcp:3389 (RDP)</strong> 허용 방화벽 규칙 필요</td>
    </tr>
  </tbody>
</table>

<!--
comment:
💬 [강사 대본]
"원본 교안 12번 장표인 VM 접속 방법 비교입니다. Linux VM은 tcp:22 포트 기반 SSH 키 인증을 사용하고, Windows VM은 tcp:3389 포트 기반 RDP 및 암호 인증을 사용합니다."
-->

---

<!-- Page 13 -->

## Compute Engine 가상 머신 수명 주기 (VM Lifecycle)

<div class="tool-hero-layout">
  <div>
    <ul>
      <li><strong>생성 및 시작 상태</strong>:
        <ul>
          <li><code>PROVISIONING</code> ➔ <code>STAGING</code> ➔ <code>RUNNING</code> (실행 중)</li>
          <li><code>instances.start()</code> 호출로 다시 시작</li>
        </ul>
      </li>
      <li><strong>정지 및 일시 중지 상태</strong>:
        <ul>
          <li><code>instances.suspend()</code> ➔ <code>SUSPENDED</code> (메모리 보관)</li>
          <li><code>instances.resume()</code> ➔ <code>RUNNING</code> (즉시 재개)</li>
        </ul>
      </li>
      <li><strong>중지 및 삭제 상태</strong>:
        <ul>
          <li><code>instances.stop()</code> ➔ <code>STOPPING</code> ➔ <code>TERMINATED</code> (종료됨)</li>
          <li><code>instances.delete()</code> ➔ 영구 삭제</li>
        </ul>
      </li>
    </ul>
  </div>
  <div class="tool-icon-box">
    <img src="data:image/png;base64,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" alt="VM Lifecycle Diagram">
    <div class="tool-icon-name">VM Lifecycle States</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"원본 교안 13번 장표인 VM 수명 주기입니다. 프로비저닝부터 스테이징, 실행, 정지(suspend), 중지(stop) 및 삭제까지 각각의 API 메서드 흐름을 이해합니다."
-->

---

<!-- Page 14 -->

## 실행 중인 VM의 상태 변경 비교 (State Changes & ACPI)

<table class="comp-table">
  <thead>
    <tr>
      <th style="width: 14%;">작업 방식</th>
      <th style="width: 20%;">실행 방법</th>
      <th style="width: 22%;">종료 스크립트 실행</th>
      <th style="width: 18%;">소요 시간</th>
      <th style="width: 26%;">상태 변화</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="header-col">재설정 (Reset)</td>
      <td>콘솔, gcloud, API, OS</td>
      <td>없음 (강제 리셋)</td>
      <td>약 0초</td>
      <td>실행 중 ➔ 실행 중</td>
    </tr>
    <tr>
      <td class="header-col">시작 (Start)</td>
      <td>콘솔, gcloud, API</td>
      <td>없음</td>
      <td>약 0초</td>
      <td>종료됨 ➔ 실행 중</td>
    </tr>
    <tr>
      <td class="header-col">재부팅 (Reboot)</td>
      <td>OS: <code>sudo reboot</code></td>
      <td>정상 실행</td>
      <td>약 90초</td>
      <td>실행 중 ➔ 실행 중</td>
    </tr>
    <tr>
      <td class="header-col">중지 (Stop)</td>
      <td>콘솔, gcloud, API</td>
      <td>ACPI 90초 대기 후 실행</td>
      <td>약 90초</td>
      <td>실행 중 ➔ 종료됨</td>
    </tr>
    <tr>
      <td class="header-col">종료 (Shutdown)</td>
      <td>OS: <code>sudo shutdown</code></td>
      <td>정상 실행</td>
      <td>약 90초</td>
      <td>실행 중 ➔ 종료됨</td>
    </tr>
    <tr>
      <td class="header-col">삭제 (Delete)</td>
      <td>콘솔, gcloud, API</td>
      <td>ACPI 90초 대기 후 실행</td>
      <td>약 90초</td>
      <td>실행 중 ➔ N/A (삭제됨)</td>
    </tr>
    <tr>
      <td class="header-col">선점 종료</td>
      <td>자동 (Spot/Preemptible)</td>
      <td>ACPI 30초 경고 후 실행</td>
      <td>약 30초</td>
      <td>실행 중 ➔ 종료됨</td>
    </tr>
  </tbody>
</table>

<!--
comment:
💬 [강사 대본]
"원본 교안 14번 장표의 VM 상태 변경 비교표입니다. 재설정, 시작, 재부팅, 중지, 종료, 삭제 및 Spot VM 선점 시 ACPI 시그널과 종료 스크립트 실행 대기 시간을 상세히 가이드합니다."
-->

---

<!-- Page 15 -->

## 가용성 정책 (Availability Policies) 및 유지보수 설정

<div class="card-grid">
  <div class="card">
    <div class="card-title">🔄 자동으로 다시 시작 (Automatic Restart)</div>
    <div class="card-desc">
      • 비정상 시스템 다운 또는 호스트 이벤트 시 <strong>자동으로 VM 인스턴스 재부팅 복구</strong><br>
      • 사용자에 의한 직접 종료나 Spot VM 선점 종료 시에는 적용되지 않음
    </div>
  </div>
  <div class="card">
    <div class="card-title">🛠️ 호스트 유지보수 시 (On Host Maintenance)</div>
    <div class="card-desc">
      • 물리 하드웨어 정기 점검 발생 시 동작 방식을 1:1 결정 (SDK/API 예약 옵션)<br>
      • <strong>라이브 마이그레이션 (Live Migration)</strong>이 기본값으로 자동 지정됨
    </div>
  </div>
  <div class="card" style="grid-column: span 2; border-left: 6px solid #1a73e8;">
    <div class="card-title" style="color: #1a73e8;">⚡ 무중단 라이브 마이그레이션 (Live Migration)</div>
    <div class="card-desc" style="font-size: 16px;">
      • 호스트 점검 도중 VM 인스턴스가 <strong>서비스 중단이나 재부팅 없이 다른 정상 하드웨어로 자동 실시간 이주</strong><br>
      • 인스턴스 메타데이터(Metadata)에 라이브 마이그레이션 발생 내역이 자동으로 기록 및 노출됨
    </div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"원본 교안 15번 장표인 가용성 정책입니다. 비정상 종료 시 자동 다시 시작, 호스트 유지보수 옵션 및 다운타임 없는 라이브 마이그레이션 메커니즘을 설명합니다."
-->

---

<!-- Page 16 -->

## Google Cloud OS 패치 관리 (OS Patch Management)

<div class="tool-hero-layout">
  <div>
    <ul>
      <li><strong>인프라 관리의 핵심 요소</strong>:
        <ul>
          <li>Google Cloud OS Config 서비스를 통해 여러 VM의 OS 패치를 쉽게 중앙 통합 관리</li>
        </ul>
      </li>
      <li><strong>주요 핵심 가치</strong>:
        <ul>
          <li>인프라 운영 환경을 항시 최신 상태로 유지</li>
          <li>보안 취약점(Vulnerability) 노출 위험 대폭 감소</li>
        </ul>
      </li>
      <li><strong>OS 패치 관리 주요 기능</strong>:
        <ul>
          <li><strong>패치 규정 준수 보고 (Compliance Reporting)</strong></li>
          <li><strong>자동 패치 배포 (Patch Deployment)</strong></li>
        </ul>
      </li>
    </ul>
  </div>
  <div class="tool-icon-box">
    <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAgAAAAIACAMAAADDpiTIAAAAeFBMVEUAAABkm/VlnvRmmfJjnPdnnfdmnfZmnfaqxv+vy/t+rPl4qfeOt/iGsfiszfuuy/qArvmuy/tonvZDhfRBh/V6qvhgmfZChfRBhfR4qPdonPWGtPiAsPlAgPKKtPhmnPaOuvl0pvhChPRChPdlm/Zdl/Z+rPhyovas+p8/AAAAKHRSTlMAM0cUH7j/cBJAyv91lEf/zHXMuDP///9H/zGYehT//3qYcB/K/3WUF+QL1gAABTZJREFUeAHs3Ed2G0kQRdHIQJHy0rTt/tfV3re8gyttIXQKPu6d0vM/VI6QwQUAAAAAAAAAAAAAAAAAAAAAAAAAAIARl2iMqNpH1WqOqtxGVUbVPMcFmuISTfUA1vUBpnqA2yP8A+dNXKCMjhAAAkAACEAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACOAYEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAATAiJN5OKJqjKjaR9VqjqrcHuEVNM9RNX+KU5niZO5HXI37OL1SAI4ABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEIAAEAACQAAIAAEgAASAABAAAkAACABXxcaYYpEncz3LT3F7Hu6jajUWrvrvMa6KHSMWuVtH1e5j3J67UV9laQCOAASAABAAAkAACAABIAAEgAAQAAJAAFxdAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAATBF2X4di3wecQQv4qwe/xFH8OnNdTwBeLx3BNhfAPYXgP0FYH8B2F8A9heA/QVgfwHYXwD2F4D9BWB/AdhfAPYXgP0FYH8B2F8A9heA/QVgfwHYXwD2F4D9BWB/AdhfAPYXgP0FYH8B2F8A9heA/QVgfwHYXwD2F4D9BWB/AdhfAPYXgP0FYP8z3BT63X+xyLN39i96/jgWufvlGE+A/+Zl1vavWs/LbBwBnv8CsL8A7C8A+wvA/gKwvwDsLwD7C8D+ArC/AOwvAPsLwP4C6LW/AOwvAPsLwP4CsL8A7C8A+wvgxX0IoPP+f/7xUACd949oXkB23797Adl+/+YFpP17F5D2711A2r93AWn/3gWk/XsXkPbvXUDav3cBaf/eBaT9exeQ9u9dQNq/dwFp/94FpP17F5D2711A2r93AWn/YgGuit3tY5En6/PvXyzg209xVk9GLDKOEsA2lvl/nH3/ayngvzeOgNPs7xRI+/cuIO3fu4C0f+8C0v69C0j79y4g7d+7gLR/7wLS/r0LSPv3LiDt37uAtH/vAtL+vQtI+/cuIO3fu4C0f+8C0v69C0j79y4g7d+7gLR/7wLS/r0LSPv3LiDt37uAtH/vAtL+vQtI+/cuIO3fu4C0f+8C0v69C0j79y4g7d+7gLR/7wLS/r0LSPv3LiDt37uAtH/vAtL+vQtI+/cuIO3fu4C0f+8C0v69CxhRltPCqdZRNb+J2/N8RNWDsXDVP70ziGsLAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAExRNs+xyCbKVo/i9qz2UbUdJ7v/dVzgVanMbxwBCAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAAASAABIAAEACuij2a9Yiq70dU/RpVP85RlT9H1Q9RNf8WVfNNBvApyl5OUfUxqt7MUfXkK75rVG0/OgIQwC0TAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIgCku0RhxeHebqBpRNg7ymQAAAAAAAAAAAAAAAAAAAAAAAAAA8GUjG4wCAHzfhQoFTr+0AAAAAElFTkSuQmCC" alt="OS Patch Management">
    <div class="tool-icon-name">OS Patch Management</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"원본 교안 16번 장표인 OS 패치 관리 개요입니다. 보안 취약점 예방을 위한 OS Config 서비스와 준수 보고서 및 자동 배포 기능을 가이드합니다."
-->

---

<!-- Page 17 -->

## OS 패치 관리를 위한 유연한 실행 작업 및 정책

<div class="card-grid">
  <div class="card">
    <div class="card-title">✅ 패치 승인 (Patch Approval)</div>
    <div class="card-desc">검증된 보안 패치 및 업데이트만 선별하여 안전하게 배포 승인 규칙 생성</div>
  </div>
  <div class="card">
    <div class="card-title">⏰ 유연한 예약 설정 (Schedules)</div>
    <div class="card-desc">서비스 영향을 최소화하기 위해 주말/야간 등 원하는 정기 점검 유지보수 시간대 지정</div>
  </div>
  <div class="card">
    <div class="card-title">⚙️ 고급 패치 구성 설정 적용</div>
    <div class="card-desc">패치 전/후 실행할 커스텀 스크립트 지정 및 OS 자동 재부팅 세부 정책 구성</div>
  </div>
  <div class="card">
    <div class="card-title">🌐 중앙 위치 통합 제어</div>
    <div class="card-desc">Google Cloud 콘솔 한 곳에서 프로젝트 내 수백 대 VM의 패치 작업 일괄 관리</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"원본 교안 17번 장표인 패치 관리 세부 작업입니다. 승인 규칙 작성, 유지보수 예약 설정, 고급 패치 구성 적용 및 중앙 통합 제어 이점을 학습합니다."
-->

---

<!-- Page 18 -->

## 중지(종료)된 VM에 대한 과금 리소스 (Billing for Stopped VMs)

<div class="card-grid">
  <div class="card" style="border-left: 6px solid #ea4335;">
    <div class="card-title" style="color: #ea4335;">❌ 과금되지 않는 리소스 (요금 0원)</div>
    <div class="card-desc" style="font-size: 17px; line-height: 1.6;">
      • <strong>CPU 연산 리소스 (vCPU)</strong><br>
      • <strong>RAM 시스템 메모리</strong><br>
      <em>* VM이 중지(STOPPED/TERMINATED) 상태인 동안에는 CPU와 RAM에 대한 비용이 전혀 청구되지 않습니다.</em>
    </div>
  </div>
  <div class="card" style="border-left: 6px solid #34a853;">
    <div class="card-title" style="color: #34a853;">💰 계속 과금되는 리소스 (요금 발생)</div>
    <div class="card-desc" style="font-size: 17px; line-height: 1.6;">
      • <strong>연결된 디스크 (Persistent Disk / Local SSD)</strong><br>
      • <strong>예약된 고정 외부 IP 주소 (Reserved Static IP)</strong><br>
      <em>* 디스크에 저장된 데이터 용량과 예약된 IP 주소 점유에 대한 요금은 지속적으로 유지됩니다.</em>
    </div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"원본 교안 18번 장표인 중지된 VM 과금 규칙입니다. CPU와 RAM 메모리는 요금이 청구되지 않지만, 데이터를 보관하는 영구 디스크와 고정 IP는 계속 요금이 발생한다는 핵심 포인트를 설명합니다."
-->

---

<!-- Page 19 -->

## 중지(종료)된 VM에서 지원되는 설정 변경 작업

<div class="card-grid">
  <div class="card">
    <div class="card-title">⚙️ 사양 & 디스크 수정</div>
    <div class="card-desc">
      • <strong>머신 유형 변경</strong>: vCPU 및 RAM 메모리 사양 조정<br>
      • <strong>연결된 디스크 추가/삭제</strong> 및 자동 삭제 설정 변경
    </div>
  </div>
  <div class="card">
    <div class="card-title">🏷️ 네트워크 & 메타데이터</div>
    <div class="card-desc">
      • <strong>인스턴스 네트워크 태그</strong> 수정<br>
      • <strong>커스텀 및 프로젝트 전체 메타데이터</strong> 수정
    </div>
  </div>
  <div class="card">
    <div class="card-title">🌐 IP & 가용성 정책</div>
    <div class="card-desc">
      • <strong>고정 IP 삭제 또는 새로 설정</strong><br>
      • <strong>가용성 정책(자동 재시작 등)</strong> 수정
    </div>
  </div>
  <div class="card" style="background: #fce8e6; border-color: #ea4335;">
    <div class="card-title" style="color: #ea4335;">⚠️ 변경 불가능한 항목</div>
    <div class="card-desc" style="color: #c5221f;">
      • <strong>중지된 VM의 OS 이미지는 변경 불가능</strong><br>
      <em>(다른 OS 이미지 적용 필요 시 신규 인스턴스 생성 필수)</em>
    </div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"원본 교안 19번 장표인 중지 상태에서의 인스턴스 설정 변경 범위입니다. 머신 타입, 디스크, 태그, 메타데이터, IP는 수정 가능하지만, OS 이미지는 변경 불가능하다는 제약사항을 전달합니다."
-->

---

<!-- Page 20 -->

## 실습 소개: Compute Engine 가상 머신 만들기 (Lab Preview)

<div class="card" style="margin-top: 10px; padding: 24px; border-left: 6px solid #1a73e8;">
  <h3 style="color: #1a73e8; font-size: 22px; margin-top:0;">🧪 실습 목표 및 주요 수행 과제</h3>
  <p style="font-size: 18px; color: #3c4043; line-height: 1.6;">
    • <strong>Google Cloud 콘솔 및 gcloud CLI 활용</strong>: Compute Engine VM 인스턴스를 직접 생성<br>
    • <strong>커스텀 인프라 구성</strong>: vCPU/메모리 머신 타입, 부팅 디스크 및 Nginx 웹 서버 설치<br>
    • <strong>SSH 접속 & 네트워크 테스트</strong>: 브라우저 SSH 접속을 통한 웹 서버 구동 및 외부 IP 수신 확인
  </p>
</div>

<!--
comment:
💬 [강사 대본]
"원본 교안 20번 장표인 실습 안내입니다. 21번 슬라이드부터 시작할 Compute Engine 가상 머신 만들기 실습의 주요 과제와 수행 절차를 소개합니다."
-->