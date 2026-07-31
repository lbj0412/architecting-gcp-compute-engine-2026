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

  /* 본문 모든 요소 강제 좌측 정렬 (표지/Q&A 제외) */
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

  /* 일반 슬라이드 제목 (H1 & H2) - 파란 밑줄(h2::after) 완전 제거! */
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

  /* 보안/경고 박스 */
  .alert-warning-box {
    background: #feefc3;
    border-left: 6px solid #fbbc04;
    border-radius: 12px;
    padding: 20px 24px;
    margin-top: 15px;
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

# Virtual Networks

### 2026 Modernized Edition | Module 02: Virtual Networks

<div class="cover-guide-box">
  Virtual Private Cloud (VPC), 서브넷, IP 주소 관리, 라우팅, 방화벽 및 Cloud NAT 종합 가이드
</div>

<div class="cover-footer-info">
  Google Cloud 교육 자료 | 베스핀글로벌 2026 개정판
</div>

<!--
comment:
💬 [강사 대본]
"수강생 여러분, 반갑습니다! 모듈 02에서는 Google Cloud 인프라 구축의 가장 중요한 뼈대인 Virtual Private Cloud (VPC) 가상 네트워크에 대해 배웁니다. 글로벌 VPC 네트워크, 서브넷 설계, 내부/외부 IP 주소 관리, 방화벽 규칙과 라우팅, 그리고 비공개 서비스 연결 및 Cloud NAT 구현까지 실무 중심으로 깊이 있게 다루겠습니다."
-->

---

<!-- Page 2 -->

## 모듈 02 학습 주제 (Agenda)

<div class="card-grid">
  <div class="card">
    <div class="card-title">01. Virtual Private Cloud (VPC)</div>
    <div class="card-desc">VPC 개념, 전역 네트워크 특징 및 구성 요소</div>
  </div>
  <div class="card">
    <div class="card-title">02. 프로젝트, 네트워크, 서브네트워크</div>
    <div class="card-desc">기본, 자동 모드 및 커스텀 모드 VPC 네트워크 비교</div>
  </div>
  <div class="card">
    <div class="card-title">03. IP 주소 관리</div>
    <div class="card-desc">내부/외부 IP 주소, 정적/임시 IP 및 Cloud DNS 연동</div>
  </div>
  <div class="card">
    <div class="card-title">04. 경로 (Routes) 및 방화벽 규칙 (Firewall Rules)</div>
    <div class="card-desc">라우팅 테이블 제어 및 상태 저장(Stateful) 방화벽 보안</div>
  </div>
  <div class="card">
    <div class="card-title">05. 네트워크 가격 책정</div>
    <div class="card-desc">이동 트래픽(Egress) 및 IP 주소 요금 산정 방식</div>
  </div>
  <div class="card">
    <div class="card-title">06. 일반적인 네트워크 설계 & 실습</div>
    <div class="card-desc">VPC 구축 및 Google Cloud NAT 비공개 액세스 구현 실습</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"모듈 02의 주요 아젠다입니다. VPC의 핵심 구조부터 네트워크 모드, IP 주소 관리, 라우팅/방화벽, 요금 모델, 그리고 실제 실습을 통한 Cloud NAT 및 Private Google Access 구현 순서로 진행됩니다."
-->

---

<!-- Page 3 -->

## Google Cloud 글로벌 인프라 위치

![bg right:48% fit](images/gcp_region_map.png)

<ul>
  <li><strong>글로벌 백본 네트워크</strong>: 전 세계 40개 이상의 리전(Region)과 에지 접속 지점(PoP) 보유</li>
  <li><strong>고가용성 구조</strong>: 리전마다 최소 3개 이상의 독립된 영역(Zone) 구성</li>
  <li><strong>전용 광케이블 사설망</strong>: 지구를 둘러싼 Google 전용 고속 백본 광케이블망 제공</li>
</ul>

<!--
comment:
💬 [강사 대본]
"Google Cloud의 네트워크는 전 세계를 구글 전용 광케이블로 연결한 글로벌 백본망입니다. 각 리전은 최소 3개의 독립된 존으로 구성되며, 수십 테라비트급의 전용 네트워크 위에서 VPC가 구동됩니다."
-->

---

<!-- Page 4 -->

## 01. Virtual Private Cloud (VPC)

<div class="tool-hero-layout">
  <div>
    <ul>
      <li><strong>Google Cloud의 핵심 가상 인프라 네트워크</strong></li>
      <li><strong>전역(Global) 범위 네트워크</strong>: 단일 VPC 네트워크가 전 세계 모든 리전에 걸쳐 작동</li>
      <li><strong>유연한 리소스 격리 및 확장</strong>: 프로젝트 단위의 완벽한 네트워크 보안 격리 지원</li>
    </ul>
  </div>
  <div class="tool-icon-box">
    <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAgAAAAIACAMAAADDpiTIAAAAZlBMVEUAAACzzP+szfucwPmCsveFsfevzfqJtviNrviuy/qavvhmnfZ2pvevyvl6qvhnnfZLivRZlPZnnfeRufhjm/dChfRWkvWKs/iGsPh6qPdypPd+rPauy/lon/WBrfdvovd2pvZwo/eQshOGAAAAInRSTlMAFEdVelwzbCb////ruP/y68+4z/X//9fR2uHEhO3f9OzxH5fXSQAAA+tJREFUeAHs3LeWFFEMRdGr8RZPxv//GQnejG2fY8V6zGqq2TtWZaeeMgUAAAAAAAAAAAAAAAAAAAAAAAAAAPgHVNqqMmT4+3mm4miRIYfLDDm464+mrY4F0HS8v90A7tO2F3aQABAAAkAACAABIAAEwBQDQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAB5mM/SfpqspW1UIAf99hpauus1UXVgAC2F0CQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgABwKfTuym/lBUAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABCAABIAAEgAAQAAJAAAgAASAABIAAcCk0OejPnle+V7P8wF26Hl9lKh5/TtdFfuDgNt+bL9NVGRod9+QwXW/zf3uZrvknKwABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAEgAAQAAJAAAgAASAABIAAEAACwKnYP1SVHipdNaUArtPDdbqOrQAEsOMEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAA4SNvRcbrqIt87rvxApevx60zFq8/pOssPnK7zvb1Zuu7n6aq07R1nSFWG1FWm4nKRIYfLDLlfWAFMLQAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAFwkMk4OU1XXWerzr54AdjZABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIBLofNKVx1nqxYCeADLq0zFpRWAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAng4AkAACAABIAAEgAAQAAJAAAgAASAAnIpd32dIVYZUJuN+kSGrZYYcLDI1AAAAAAAAAAAAAAAAAAAAAAAAAABsNrLBKAAApegykzmGVsoAAAAASUVORK5CYII=" alt="VPC">
    <div class="tool-icon-name">Virtual Private Cloud</div>
    <div style="font-size: 14px; color: #5f6368; margin-top: 6px;">Global Software-Defined Network</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"첫 번째 주제인 Virtual Private Cloud, 즉 VPC입니다. 타 클라우드와 달리 Google Cloud의 VPC는 전 세계 모든 리전을 커버하는 '전역(Global)' 네트워크입니다. 단 하나의 VPC 안에서 미국, 한국, 유럽의 VM들이 내부 IP로 직접 통신할 수 있습니다."
-->

---

<!-- Page 5 -->

## VPC 네트워크 구성 객체 (VPC Objects)

<div class="card-grid-3">
  <div class="card">
    <div class="card-title">🌐 조직 / 프로젝트</div>
    <div class="card-desc">GCP 리소스 및 결제 계정을 연결하는 최상위 바운더리</div>
  </div>
  <div class="card">
    <div class="card-title">🔌 네트워크 (Networks)</div>
    <div class="card-desc">기본, 자동 모드, 커스텀 모드로 구성되는 전역 네트워크</div>
  </div>
  <div class="card">
    <div class="card-title">🗺️ 서브네트워크 (Subnets)</div>
    <div class="card-desc">특정 리전에 종속되는 IP 주소 대역 분할 공간</div>
  </div>
  <div class="card">
    <div class="card-title">🔢 IP 주소 (IP Addresses)</div>
    <div class="card-desc">내부/외부 IP, 임시(Ephemerl)/정적(Static) IP 주소 범위</div>
  </div>
  <div class="card">
    <div class="card-title">🛤️ 경로 (Routes)</div>
    <div class="card-desc">패킷이 목적지 IP로 도달하기 위한 라우팅 규칙</div>
  </div>
  <div class="card">
    <div class="card-title">🛡️ 방화벽 규칙 (Firewalls)</div>
    <div class="card-desc">상태 저장(Stateful) 방식의 트래픽 차단/허용 보안 정책</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"VPC를 구성하는 핵심 객체들입니다. 프로젝트, 전역 네트워크, 리전별 서브넷, 내부/외부 IP 주소, 라우팅 경로, 그리고 방화벽 규칙이 유기적으로 조화되어 안전한 인프라를 만듭니다."
-->

---

<!-- Page 6 -->

## 02. 프로젝트, 네트워크, 서브네트워크

<div class="card" style="margin-top: 20px; padding: 30px; border-left: 6px solid #1a73e8;">
  <h3 style="color: #1a73e8; font-size: 26px; margin-top: 0;">🏢 프로젝트 및 네트워크의 관계</h3>
  <p style="font-size: 20px; color: #3c4043; line-height: 1.7;">
    • <strong>프로젝트 (Project)</strong>: GCP 리소스 및 서비스 결제를 연결하며 프로젝트당 최대 15개 네트워크 보유 가능<br>
    • <strong>네트워크 (Network)</strong>: 자체 IP 주소 범위를 가지지 않으며 전 세계 모든 리전에 걸쳐 확장되는 전역 리소스<br>
    • <strong>서브네트워크 (Subnet)</strong>: 특정 리전 내에 정의되는 IP 주소 범위이며 여러 영역(Zone)에 걸쳐 적용 가능
  </p>
</div>

<!--
comment:
💬 [강사 대본]
"프로젝트와 네트워크, 서브넷의 관계를 명확히 이해해야 합니다. 네트워크 자체는 IP 범위를 가지지 않으며, 전 세계 리전에 배치되는 서브넷들의 집합체 역할을 수행합니다."
-->

---

<!-- Page 7 -->

## VPC 네트워크 3가지 모드 비교 (VPC Network Types)

| 구분 | 기본 모드 (Default) | 자동 모드 (Auto Mode) | 커스텀 모드 (Custom Mode) |
| :--- | :--- | :--- | :--- |
| **서브넷 자동 생성** | 리전당 1개 자동 생성 (/20) | 리전당 1개 자동 생성 (/20) | **생성 안 됨 (사용자 직접 지정)** |
| **기본 방화벽 규칙** | 사전 정의 방화벽 규칙 포함 | 방화벽 규칙 직접 설정 필요 | 방화벽 규칙 직접 설정 필요 |
| **IP 범위 제어** | 고정 /20 CIDR 대역 | /16 대역까지 확장 가능 | **IP 범위를 100% 완전 자유 제어** |
| **권장 유즈케이스** | 빠른 테스트 및 기본 체험 | 초기 프로토타입 개발 | **엔터프라이즈 운영 (강력 권장)** |

<!--
comment:
💬 [강사 대본]
"VPC 네트워크의 3가지 모드 비교입니다. 실무 프로젝트에서는 IP 대역 충돌을 방지하고 정교한 보안 정책을 수립할 수 있는 '커스텀 모드(Custom Mode)' 사용을 강력히 권장합니다."
-->

---

<!-- Page 8 -->

## 글로벌 시스템 격리 및 통신 방식

<div class="card-grid">
  <div class="card">
    <div class="card-title">🌐 동일 VPC 내 리전 간 내부 통신</div>
    <div class="card-desc">VM A(서울)와 VM B(오리건)가 서로 다른 리전에 있어도 **동일 VPC 내에서는 고속 내부 IP(Private IP)로 직접 무료 통신** 가능</div>
  </div>
  <div class="card">
    <div class="card-title">🔒 서로 다른 VPC 간 통신</div>
    <div class="card-desc">VM C와 VM D가 동일한 리전에 있더라도 서로 다른 VPC에 속해 있다면 **외부 IP(Public IP) 또는 VPC Peering을 통해서만 통신** 가능</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"GCP 전역 VPC의 가장 놀라운 특징입니다. 서울과 오리건에 있는 VM이라도 동일한 VPC 안에 있다면 암호화된 구글 백본망을 통해 내부 IP로 직접 빠른 통신이 가능합니다."
-->

---

<!-- Page 9 -->

## 서브네트워크의 영역(Zone) 교차 특성

<div class="card" style="margin-top: 20px; padding: 30px; border-left: 6px solid #34a853;">
  <h3 style="color: #34a853; font-size: 26px; margin-top: 0;">✅ 서브넷은 리전 범위이며, 모든 영역(Zone)을 포함합니다</h3>
  <p style="font-size: 20px; color: #3c4043; line-height: 1.7;">
    • 동일한 서브넷에 속한 VM 인스턴스라도 서울 리전의 <strong>asia-northeast3-a, b, c 등 서로 다른 영역(Zone)에 배치</strong>할 수 있습니다.<br>
    • 따라서 하나의 서브넷에 대해 <strong>단일 방화벽 규칙을 정의하면 여러 영역에 분산된 모든 VM에 일괄 적용</strong>됩니다.
  </p>
</div>

<!--
comment:
💬 [강사 대본]
"서브넷은 리전 단위에 속하므로, 하나의 서브넷 IP 대역 안에서 a, b, c 여러 존에 VM을 자유롭게 나눌 수 있습니다. 덕분에 방화벽 규칙 하나로 여러 존의 VM을 동시에 보호할 수 있습니다."
-->

---

<!-- Page 10 -->

## 인스턴스 중단 없는 서브넷 CIDR 무중단 확장

<div class="card" style="margin-top: 20px; padding: 30px; border-left: 6px solid #1a73e8;">
  <h3 style="color: #1a73e8; font-size: 26px; margin-top: 0;">📈 서브넷 IP 대역 확장 규칙 (Subnet Expansion)</h3>
  <p style="font-size: 19px; color: #3c4043; line-height: 1.6;">
    1. <strong>VM 중단 없음</strong>: 실행 중인 가상 머신의 재부팅이나 삭제 없이 서브넷 CIDR 대역을 무중단 확장 가능<br>
    2. <strong>단방향 확장</strong>: IP 대역을 <strong>확장할 수는 있지만 축소할 수는 없음</strong> (예: /24 ➔ /22 가능)<br>
    3. <strong>고유성 유지</strong>: 다른 서브넷의 IP 대역과 중복될 수 없으며 유효한 CIDR 블록 내에 존재해야 함
  </p>
</div>

<!--
comment:
💬 [강사 대본]
"서비스 운영 중 IP가 부족해지면 VM을 끄지 않고도 서브넷 대역을 무중단 확장할 수 있습니다. 단, 한 번 넓힌 대역은 다시 줄일 수 없으므로(단방향) 처음 설계 시 신중해야 합니다."
-->

---

<!-- Page 11 -->

## 03. IP 주소 관리 (IP Addressing)

<div class="card-grid">
  <div class="card">
    <div class="card-title">🔹 내부 IP 주소 (Private IP)</div>
    <div class="card-desc">
      • DHCP를 통해 서브넷 범위에서 VM에 자동으로 할당<br>
      • DHCP 임대는 24시간마다 자동 갱신되며, internal DNS에 자동 등록<br>
      • 동일 VPC 내부 및 연결된 네트워크 간 고속 통신에 사용
    </div>
  </div>
  <div class="card">
    <div class="card-title">🔸 외부 IP 주소 (Public IP)</div>
    <div class="card-desc">
      • 인터넷 통신을 위해 구글 IP 풀에서 할당<br>
      • **임시 IP (Ephemeral)**: VM 중지 시 반납됨<br>
      • **정적 IP (Static)**: 고정 IP로 사전 예약하여 영구 유지<br>
      • 자체 IP 가져오기 (BYOIP) 지원
    </div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"세 번째 주제인 IP 주소 관리입니다. 내부 IP는 VPC 안에서의 고속 통신을 전담하고, 외부 IP는 인터넷 액세스 및 외부 사용자의 웹 서비스 접속을 위해 1:1 NAT 방식으로 할당됩니다."
-->

---

<!-- Page 12 -->

## 내부 DNS 자동 변환 (Internal DNS Resolution)

<div class="card" style="margin-top: 20px; padding: 30px; border-left: 6px solid #1a73e8;">
  <h3 style="color: #1a73e8; font-size: 24px; margin-top:0;">🌐 FQDN 호스트 이름 구조</h3>
  <p style="font-size: 19px; color: #202124; font-family: monospace; background: #f1f3f4; padding: 12px; border-radius: 8px;">
    [hostname].[zone].c.[project-id].internal
  </p>
  <p style="font-size: 18px; color: #3c4043; line-height: 1.6; margin-top: 12px;">
    • 예시: `my-server.asia-northeast3-a.c.my-project-123.internal`<br>
    • GCP 내부 DNS 리졸버 IP: <strong>169.254.169.254</strong> (Compute Engine 메타데이터 서버 연동)
  </p>
</div>

<!--
comment:
💬 [강사 대본]
"VM이 생성되면 구글 내부 DNS가 FQDN 형태의 내부 호스트 이름을 자동 등록해 줍니다. 169.254.169.254 가상 리졸버를 통해 IP 주소가 바뀌어도 인스턴스 이름으로 즉시 통신이 가능합니다."
-->

---

<!-- Page 13 -->

## Cloud DNS를 활용한 외부 domain 영역 호스팅

<div class="tool-hero-layout">
  <div>
    <ul>
      <li><strong>Google의 고성능 관리형 DNS 서비스</strong></li>
      <li><strong>100% 업타임 SLA 보장</strong>: 글로벌 에지 네트워크를 통한 짧은 지연 시간 및 초고가용성</li>
      <li><strong>대규모 DNS 레코드 관리</strong>: 수백만 개의 A, CNAME, MX 레코드 자동 생성 및 업데이트 API 지원</li>
    </ul>
  </div>
  <div class="tool-icon-box">
    <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAgAAAAIACAMAAADDpiTIAAAAb1BMVEUAAACzzP+szfuCsveStvWuy/pmnfaLtffY5v3o8f7///+vzfqvyvmryfqlxPl1pvh2p/d2pveNtPZBhfRChfSkw/mQt/hypPd1pviAsPlgmfZhmvZzqPeuy/lonPZlnvadwfllnvSavviszfmvy/t4akk+AAAAJXRSTlMAFEd6Mf//mP///zO4vcrw7et0R//M///xev//n7c2v+1H/y5AcTN9rgAAA61JREFUeAHs3IFGBFEUx+H/2RmRAKGo6v1fq0pBAbDaTA8Q3Nibvbfve4M7fs6BccIJAAAAAAAAAAAAAAAAAAAAAAAAAACASrOqTGjORx16vH+3ZBAC2KfVLsxPAAgAASAABIAAEAACQAAIQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABjCmh6WSqtDmC+AqmAFIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAH05FKo+68mAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAHVSaXVSGVtX8AWr0p370CGB0l5VW27sVgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAU7GdnP/iVOzeqdifdksmVJlQ7a0ARgsAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAArOlhrbT6DCYAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEABZ08OWf00AX/kNrAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgACrNqjK0q2r+APWaodWhRwCju6y02t6tAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAA/lZlRndvOb7rJxPgVCEABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgABY0+y+/vevrstDRrE99ghgeckobtPB7jmjuLECGC4ABIAAEAACQAAIAAEgAASAABAAAkAACAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgAASAABAAAkAACAABUJnR3VuO7/rJBDhVCAABIAAEgAAQAAJAAAgAASAABIAAEAACQAAIAAEgANbM6Owhx7cFAAAAAAAAAAAAAAAAAAAAAAAAAAD6+d7IBqMAADnRHaezP2CeAAAAAElFTkSuQmCC" alt="Cloud DNS">
    <div class="tool-icon-name">Cloud DNS</div>
    <div style="font-size: 14px; color: #5f6368; margin-top: 6px;">100% SLA Managed DNS</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"외부 사용자에게 웹 서비스를 공개할 때 사용하는 Cloud DNS입니다. 100% 업타임 SLA를 제공하며, 구글의 글로벌 에지 인프라에서 수밀리초 내에 도메인을 IP로 변환해 줍니다."
-->

---

<!-- Page 14 -->

## 04. 경로 (Routes) 및 방화벽 규칙 (Firewall Rules)

<div class="card-grid">
  <div class="card">
    <div class="card-title">🛤️ 경로 (Routes)</div>
    <div class="card-desc">
      • 패킷이 원하는 목적지 IP 대역으로 가기 위한 라우팅 테이블<br>
      • **기본 경로**: 서브넷 간 통신 및 0.0.0.0/0 인터넷 게이트웨이 경로 자동 생성<br>
      • **사용자 정의 경로**: VPN, Cloud NAT, 가상 방화벽 어플라이언스로 트래픽 전달
    </div>
  </div>
  <div class="card">
    <div class="card-title">🛡️ 방화벽 규칙 (Firewall Rules)</div>
    <div class="card-desc">
      • **상태 저장(Stateful) 방식**: 요청 트래픽이 허용되면 응답 트래픽은 자동 허용<br>
      • **분산형 방화벽**: 중앙 집중 병목 없이 각 VM 인스턴스 수준에서 직접 처리<br>
      • Network Tags 및 Service Account 기반 정교한 대상 지정 지원
    </div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"네 번째 주제인 라우팅과 방화벽입니다. 라우팅은 패킷의 이정표 역할을 하며, 방화벽은 분산형 상태 저장(Stateful) 방식으로 동작하여 VM 단위로 인바운드/아웃바운드 보안을 처리합니다."
-->

---

<!-- Page 15 -->

## 05. 네트워크 가격 책정 (Pricing)

<div class="card-grid-3">
  <div class="card">
    <div class="card-title">🟢 무료 트래픽 (Free)</div>
    <div class="card-desc">VPC 내부 인바운드 트래픽 및 동일 Zone 내 내부 IP 트래픽 무료</div>
  </div>
  <div class="card">
    <div class="card-title">🟡 리전 간 이동 (Egress)</div>
    <div class="card-desc">서로 다른 리전 간 VM 데이터 이동 시 GB당 네트워크 전송 요금 발생</div>
  </div>
  <div class="card">
    <div class="card-title">🔴 정적 외부 IP 미사용 요금</div>
    <div class="card-desc">예약된 정적 외부 IP를 VM에 할당하지 않고 방치할 경우 미사용 수수료 부과</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"네트워크 요금 모델입니다. 인바운드는 100% 무료이지만, 인터넷이나 타 리전으로 나가는 아웃바운드(Egress) 트래픽은 비용이 발생합니다. 특히 안 쓰는 고정 IP를 켜두면 미사용 요금이 청구되므로 즉시 반납해야 합니다."
-->

---

<!-- Page 16 -->

## 06. 일반적인 네트워크 설계 & 실습

<div class="card" style="margin-top: 20px; padding: 30px; border-left: 6px solid #1a73e8;">
  <h3 style="color: #1a73e8; font-size: 26px; margin-top: 0;">🧪 Lab 02. Implementing Private Google Access & Cloud NAT</h3>
  <p style="font-size: 19px; color: #3c4043; line-height: 1.6;">
    • <strong>실습 목표</strong>: 외부 IP 주소가 없는 비공개 VM(Private VM)이 안전하게 패키지를 업데이트하고 Google Cloud API에 접속하는 아키텍처 구축<br>
    • <strong>주요 구성 기술</strong>:<br>
      1. <strong>Private Google Access</strong>: 외부 IP 없이 내부 IP로 Cloud Storage 버킷에 직접 접속<br>
      2. <strong>Google Cloud NAT</strong>: 외부 IP가 없는 VM에 아웃바운드 인터넷 게이트웨이 통로 제공
  </p>
</div>

<!--
comment:
💬 [강사 대본]
"모듈 02의 핵심 실습입니다! 외부 IP가 없는 비공개 VM을 만들고, Private Google Access와 Cloud NAT을 구축하여 보안을 유지하면서 아웃바운드 인터넷 업그레이드를 수행해 보겠습니다."
-->

---

<!-- Page 17 -->

## Cloud NAT (Network Address Translation) 아키텍처

<div class="tool-hero-layout">
  <div>
    <ul>
      <li><strong>완전 관리형 풀 매니지드 NAT 서비스</strong></li>
      <li><strong>보안 우수성</strong>: 외부에서 내부 VM으로 들어오는 인바운드 접속은 100% 차단</li>
      <li><strong>아웃바운드 전용 통로</strong>: 비공개 VM이 OS 패치, 소프트웨어 업데이트를 위해 외부 인터넷으로 나갈 때 사용</li>
      <li><strong>고가용성 & 자동 스케일링</strong>: 게이트웨이 VM 관리 부담 없이 구글 백본에서 자동 분산 처리</li>
    </ul>
  </div>
  <div class="tool-icon-box">
    <img src="data:image/png;base64,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" alt="Cloud NAT">
    <div class="tool-icon-name">Cloud NAT</div>
    <div style="font-size: 14px; color: #5f6368; margin-top: 6px;">Managed Outbound NAT</div>
  </div>
</div>

<!--
comment:
💬 [강사 대본]
"Cloud NAT 서비스입니다. 외부 해커의 침입은 100% 차단하면서, 내부 VM이 안전하게 외부 소프트웨어 패치를 다운로드받을 수 있도록 아웃바운드 NAT 통로를 완벽 제공합니다."
-->

---

<!-- Page 18 -->

## 복습 퀴즈 01 (Review Question 1)

<div class="card" style="margin-top: 20px; padding: 30px;">
  <h3 style="color: #202124; font-size: 24px; margin-top:0;">❓ Q1. Google Cloud의 Virtual Private Cloud (VPC) 범위에 대한 올바른 설명은 무엇인가요?</h3>
  <p style="font-size: 20px; color: #3c4043; line-height: 1.8;">
    A. 하나의 단일 영역(Zone)에만 국한된다.<br>
    B. 하나의 단일 리전(Region)에만 생성할 수 있다.<br>
    C. <strong>전 세계 모든 리전에 걸쳐 확장되는 전역(Global) 리소스이다.</strong><br>
    D. 온프레미스 데이터센터 내부에서만 동작한다.
  </p>
</div>

<!--
comment:
💬 [강사 대본]
"모듈 02 첫 번째 복습 퀴즈입니다. Google Cloud VPC 네트워크의 작동 범위에 대한 가장 핵심적인 특성을 골라보세요."
-->

---

<!-- Page 19 -->

## 복습 퀴즈 01 정답 및 해설

<div class="card" style="margin-top: 20px; padding: 30px; border-left: 6px solid #34a853;">
  <h3 style="color: #34a853; font-size: 26px; margin-top:0;">✅ 정답: C</h3>
  <p style="font-size: 20px; color: #3c4043; line-height: 1.7;">
    • <strong>C (정답)</strong>: Google Cloud의 VPC는 단일 프로젝트 내에서 전 세계 모든 리전을 커버하는 **전역(Global) 소프트웨어 정의 네트워크**입니다.<br>
    • <strong>A, B (오답)</strong>: 타 클라우드와 달리 리전이나 존 단위에 갇히지 않고 전 세계로 확장됩니다.<br>
    • <strong>D (오답)</strong>: Google Cloud 인프라 기반 서비스입니다.
  </p>
</div>

<!--
comment:
💬 [강사 대본]
"정답은 C번입니다! Google Cloud의 VPC는 전 세계 모든 리전에 걸쳐 확장되는 전역 네트워크라는 점을 반드시 기억해 주세요."
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

### 다음 장표: Module 03. Virtual Machines (Compute Engine VM)

<div class="cover-footer-info">
  Google Cloud 교육 자료 | 베스핀글로벌 2026 개정판
</div>

<!--
comment:
💬 [강사 대본]
"이상으로 모듈 02 Virtual Networks 개정 수업을 마치겠습니다. 10분간 휴식하신 후 모듈 03에서는 Compute Engine 가상 머신(VM) 구축과 라이브 마이그레이션 실습에 대해 배웁니다. 수고하셨습니다!"
-->
