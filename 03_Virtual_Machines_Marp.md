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
    padding: 70px 80px 50px 80px;
    font-size: 22px;
    line-height: 1.55;
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

  section:not(.lead) p,
  section:not(.lead) ul,
  section:not(.lead) ol,
  section:not(.lead) li,
  section:not(.lead) div,
  section:not(.lead) .agenda-list-item,
  section:not(.lead) h3,
  section:not(.lead) table {
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

  section.lead h1 {
    color: #ffffff !important;
    font-size: 50px;
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
    font-size: 26px;
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
    font-size: 18px;
    font-weight: 600;
    margin-top: 10px;
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.25);
    text-align: center !important;
    backdrop-filter: blur(8px);
  }

  .cover-footer-info {
    position: absolute;
    bottom: 30px;
    right: 50px;
    font-size: 14px;
    color: #9aa0a6;
    font-weight: 500;
  }

  h1, h2 {
    color: #1a73e8;
    font-size: 34px;
    font-weight: 800;
    margin-top: 0;
    margin-bottom: 22px;
    letter-spacing: -0.03em;
  }

  /* Agenda List Layout (전형적인 깔끔한 목차 형태) */
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

  ul {
    list-style: none;
    padding-left: 0;
    margin-top: 0;
  }
  li {
    position: relative;
    padding-left: 28px;
    margin-bottom: 12px;
    font-weight: 500;
    letter-spacing: -0.02em;
    font-size: 20px;
  }
  li::before {
    content: '';
    position: absolute;
    left: 4px;
    top: 11px;
    width: 8px;
    height: 8px;
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
"모듈 03의 학습 목차입니다. VM 옵션부터 액세스 관리, 스토리지, 라이브 마이그레이션, Spot VM 요금 모델, 그리고 실제 VM 생성 실습 순서로 한눈에 명확히 진행됩니다."
-->

---

<!-- Page 3 -->

## 01. Compute Engine 옵션 & 머신 패밀리

<div class="tool-hero-layout">
  <div>
    <ul>
      <li><strong>Google Cloud의 대표 IaaS 서비스 (Virtual Machines)</strong></li>
      <li><strong>유연한 커스텀 사양 구성</strong>: 요구사항에 맞는 vCPU 및 RAM 메모리 맞춤 조합</li>
      <li><strong>2026 최신 머신 패밀리 분류</strong>:
        <ul>
          <li>범용 (General-purpose): N2, N4, E2 (균형잡힌 워크로드)</li>
          <li>컴퓨팅 최적화 (Compute-optimized): C2, C3, C4 (고성능 웹/게임)</li>
          <li>메모리 최적화 (Memory-optimized): M2, M3 (In-memory DB/SAP)</li>
          <li>가속기 최적화 (Accelerator-optimized): A2, A3 (NVIDIA H100 AI/ML)</li>
        </ul>
      </li>
    </ul>
  </div>
  <div class="tool-icon-box">
    <img src="data:image/png;base64,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" alt="Compute Engine">
    <div class="tool-icon-name">Compute Engine</div>
    <div style="font-size: 14px; color: #5f6368; margin-top: 6px;">2026 Modernized IaaS</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"Compute Engine은 다양한 가상 머신 옵션을 제공합니다. 업무 특성에 따라 범용 N4, 고성능 C4, 메모리 M3, AI 전용 A3 GPU 인스턴스를 자유롭게 조립할 수 있습니다."
-->

---

<!-- Page 4 -->

## Compute Engine 가상 머신의 주요 특징

<div class="tool-hero-layout">
  <div>
    <ul>
      <li><strong>초고속 부팅 속도</strong>: 불과 수초 내에 VM 인스턴스가 생성되고 부팅 완료</li>
      <li><strong>독립적인 영구 디스크 (Persistent Disk)</strong>: VM과 수명주기가 독립된 안전한 블록 스토리지</li>
      <li><strong>글로벌 백본 네트워크 연동</strong>: 전 세계 구글 전용 사설 네트워크망을 통한 빠른 통신</li>
      <li><strong>전용 OS 이미지 지원</strong>: Debian, Ubuntu, RHEL, Windows Server 및 커스텀 이미지 활용</li>
    </ul>
  </div>
  <div class="tool-icon-box">
    <img src="data:image/png;base64,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" alt="Google Cloud SSD">
    <div class="tool-icon-name">VM Infrastructure</div>
    <div style="font-size: 14px; color: #5f6368; margin-top: 6px;">Module 03 Slide 04</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"Compute Engine VM의 주요 특징입니다. 수초 내 부팅, 독립된 영구 디스크, 글로벌 백본 연동 및 다양한 OS 이미지를 즉시 활용할 수 있습니다."
-->

---

<!-- Page 5 -->

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

<!-- Page 6 -->

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

<!-- Page 7 -->

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

<!-- Page 8 -->

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

---

<!-- Page 9 -->

## 커스텀 머신 유형 만들기 (Custom Machine Types)

<div class="card-grid">
  <div class="card">
    <div class="card-title">⚙️ 맞춤형 사양 조합</div>
    <div class="card-desc">사전 정의된 규격에 구애받지 않고, 애플리케이션에 필요한 정확한 vCPU와 메모리를 1:1 맞춤 설계</div>
  </div>
  <div class="card">
    <div class="card-title">💡 비용 효율성 극대화</div>
    <div class="card-desc">불필요하게 과도한 머신 등급을 선택하지 않음으로써 오버프로비저닝을 방지하고 비용 절감</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"Compute Engine의 자랑인 커스텀 머신 사양 만들기입니다. 필요한 CPU와 메모리만 딱 맞춰 구매하므로 낭비되는 예산을 완벽히 막을 수 있습니다."
-->

---

<!-- Page 10 -->

## Compute Engine 가상 머신 스토리지 및 구조

<div class="tool-hero-layout">
  <div>
    <ul>
      <li><strong>독립된 블록 스토리지 아키텍처</strong>:
        <ul>
          <li><strong>Persistent Disk (PD)</strong>: 네트워크 연결 블록 스토리지 (Standard / Balanced / SSD)</li>
          <li><strong>Local SSD</strong>: 물리 서버에 직접 탑재된 초고속 NVMe 캐시 디스크</li>
        </ul>
      </li>
      <li><strong>차세대 Hyperdisk (2026)</strong>: IOPS와 스루풋 성능을 개별 동적 제어</li>
    </ul>
  </div>
  <div class="tool-icon-box">
    <img src="data:image/png;base64,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" alt="Block Storage">
    <div class="tool-icon-name">Storage Architecture</div>
    <div style="font-size: 14px; color: #5f6368; margin-top: 6px;">Module 03 Slide 10</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"10번 장표에서는 Compute Engine VM의 스토리지 구조를 보여줍니다. 독립된 Persistent Disk와 초고속 Local SSD가 조합되어 완벽한 인프라를 형성합니다."
-->