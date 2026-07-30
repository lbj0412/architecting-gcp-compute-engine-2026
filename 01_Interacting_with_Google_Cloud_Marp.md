---
marp: true
theme: uncover
paginate: true
header: 'Google Cloud Training Series'
footer: 'Architecting with Google Compute Engine © 2026'
style: |
  @import url('https://fonts.googleapis.com/css2?family=Pretendard:wght@300;400;600;700;800&display=swap');
  
  section {
    font-family: 'Pretendard', sans-serif;
    background: linear-gradient(135deg, #f8f9fa 0%, #e8f0fe 100%);
    color: #202124;
    padding: 60px 80px;
    text-align: left;
    font-size: 26px;
    line-height: 1.6;
  }
  
  header {
    font-size: 14px;
    font-weight: 700;
    color: #1a73e8;
    letter-spacing: 1px;
    text-transform: uppercase;
  }
  footer {
    font-size: 13px;
    color: #70757a;
  }

  section.lead {
    background: linear-gradient(135deg, #1a73e8 0%, #0d47a1 100%);
    color: #ffffff;
    text-align: left;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  section.lead h1 {
    color: #ffffff;
    font-size: 56px;
    font-weight: 800;
    line-height: 1.2;
    margin-bottom: 20px;
  }
  section.lead h3 {
    color: #8ab4f8;
    font-size: 24px;
    font-weight: 600;
    margin-bottom: 30px;
  }

  h1, h2 {
    color: #1a73e8;
    font-size: 40px;
    font-weight: 700;
    margin-bottom: 30px;
    letter-spacing: -0.5px;
  }
  
  h2::after {
    content: '';
    display: block;
    width: 60px;
    height: 4px;
    background: #4285f4;
    margin-top: 10px;
    border-radius: 2px;
  }

  ul {
    list-style: none;
    padding-left: 0;
  }
  li {
    position: relative;
    padding-left: 32px;
    margin-bottom: 16px;
    font-weight: 400;
  }
  li::before {
    content: '◆';
    position: absolute;
    left: 0;
    color: #1a73e8;
    font-size: 18px;
  }

  .card {
    background: #ffffff;
    border-radius: 16px;
    padding: 24px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
    border: 1px solid rgba(26, 115, 232, 0.15);
    margin-bottom: 20px;
  }
  
  .card-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
  }

  table {
    width: 100%;
    border-collapse: separate;
    border-spacing: 0;
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.05);
    background: #ffffff;
    font-size: 20px;
    margin-top: 20px;
  }
  th {
    background: #1a73e8;
    color: #ffffff;
    font-weight: 700;
    padding: 16px;
    text-align: left;
  }
  td {
    padding: 16px;
    border-bottom: 1px solid #e8eaed;
    color: #3c4043;
  }
  tr:last-child td { border-bottom: none; }
  tr:nth-child(even) { background-color: #f8f9fa; }
  
  img {
    border-radius: 16px;
    box-shadow: 0 12px 32px rgba(0, 0, 0, 0.15);
  }
  
  .quiz-box {
    background: #ffffff;
    border-left: 6px solid #1a73e8;
    border-radius: 12px;
    padding: 20px 28px;
    box-shadow: 0 8px 24px rgba(0,0,0,0.06);
    margin-top: 15px;
  }
---

<!-- _class: lead -->

# Module 01.<br>Interacting with Google Cloud
### 2026 Modernized Edition | Google Cloud와 상호작용하기

![bg right:42% fit](https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=800)

구글 클라우드를 리소스 및 서비스를 제어하는 4가지 핵심 인터페이스 가이드

---

## 📌 개요 (Overview)

Google Cloud의 리소스(VM, Storage, VPC 등)를 관리하고 배포하는 **4가지 인터페이스**를 학습합니다.

<div class="card-grid">
  <div class="card">
    <strong>1. Google Cloud 콘솔 (GUI)</strong><br>
    웹 기반 직관적 그래픽 관리 환경
  </div>
  <div class="card">
    <strong>2. Cloud Shell & gcloud CLI</strong><br>
    브라우저 통합 웹 IDE & CLI
  </div>
  <div class="card">
    <strong>3. Client Libraries & REST API</strong><br>
    코드 기반 자동화 및 프로그래밍 제어
  </div>
  <div class="card">
    <strong>4. Cloud Mobile App & IaC</strong><br>
    모바일 대시보드 및 Terraform 자동화
  </div>
</div>

---

## 01. Google Cloud 콘솔 (Console GUI)

![bg right:40% fit](https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=800)

* **웹 기반 중앙 집중식 관리 도구**
  * `console.cloud.google.com` 접속
* **핵심 기능**
  * **탐색 메뉴 (Navigation Menu)**: 컴퓨팅, 스토리지, 네트워크 등 서비스 분류
  * **프로젝트 선택기**: 조직 및 프로젝트 단위 독립 환경 스위칭
  * **Cloud Shell 통합 버튼**: 클릭 한 번으로 대화형 CLI 즉시 구동

---

## 02. Cloud Shell & gcloud CLI

![bg right:42% fit](https://images.unsplash.com/photo-1629654297299-c8506221ca97?w=800)

* **Cloud Shell (웹 CLI & Cloud Shell Editor)**
  * **5GB 영구 디스크 storage** 무료 제공
  * VS Code 기반 **Cloud Shell Editor** 내장
* **gcloud CLI (Cloud SDK)**
  * `gcloud compute instances list`
  * `gcloud storage buckets create`
  * 최신 `gcloud` 구성 요소 관리 및 인증 자동 처리

---

## 03. API & 개발자 라이브러리 (Client Libraries)

![bg right:40% fit](https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=800)

* **Google Cloud Client Libraries**
  * Python, Node.js, Java, Go, C# 등 언어별 최적화 SDK
  * 내장 인증 처리 및 성능/오류 재시도 로직 자동 적용
* **RESTful API / gRPC API**
  * OAuth 2.0 기반의 강력한 보안 스키마
  * JSON / Protocol Buffer 응답 규격 지원

---

## 04. 인터페이스 비교 (Comparison Matrix)

| 구분 | Cloud 콘솔 (GUI) | Cloud Shell / gcloud (CLI) | Cloud Client Libraries (API) |
| :--- | :--- | :--- | :--- |
| **주요 대상** | 초보자, 시각적 작업 | SysOps, DevOps, 스크립터 | 소프트웨어 개발자, 시스템 통합 |
| **장점** | 학습 곡선 낮음, 대시보드 | 빠른 배치 스크립팅, 자동화 | 앱 내부 깊은 연동, 대규모 제어 |
| **대표 사례** | 상태 모니터링, 신규 리소스 생성 | 리소스 관리 CLI 스크립트 작성 | 앱 내 파일 업로드 API 개발 |

---

## 🧪 실습 01: Console과 Cloud Shell 시작하기

![bg right:38% fit](https://images.unsplash.com/photo-1517694712202-14dd9538aa97?w=800)

* **실습 목표**
  1. Google Cloud 콘솔 및 프로젝트 ID 확인
  2. GCP Console을 사용한 Cloud Storage 버킷 생성
  3. Cloud Shell 터미널 접속 및 `gsutil` / `gcloud` 명령어 실행
  4. Cloud Shell Editor 환경 탐색

---

## 🧪 실습 02: 인프라 미리보기 & Marketplace

![bg right:38% fit](https://images.unsplash.com/photo-1504384308090-c894fdcc538d?w=800)

* **실습 목표**
  1. **Google Cloud Marketplace** 솔루션 탐색
  2. 클릭 몇 번으로 CI/CD 툴(Jenkins/GitLab) 자동 배포
  3. 생성된 VM 인스턴스에 SSH 접속 및 헬스 체크

---

## ❓ 자가 점검 퀴즈 (Quiz 1)

<div class="quiz-box">
  <strong>Q. Google Cloud와 상호작용하기 위해 로컬 PC 설치 없이 브라우저에서 5GB의 영구 스토리지와 함께 명령줄 환경을 제공하는 서비스는 무엇인가요?</strong><br><br>
  A. Google Cloud Mobile App<br>
  B. Google Cloud Shell<br>
  C. Cloud Console Dashboard<br>
  D. Google Compute Engine VM
</div>

---

## 💡 퀴즈 정답 및 해설 (Quiz 1 Answer)

<div class="card">
  <strong style="color: #34a853; font-size: 28px;">정답: B. Google Cloud Shell</strong><br><br>
  <strong>해설:</strong> Google Cloud Shell은 별도의 로컬 터미널 환경 설정 없이 브라우저상에서 바로 사용할 수 있는 임시 Compute VM 기반의 CLI 솔루션이며, 사용자 홈 디렉토리에 5GB의 영구 디스크 공간을 기본으로 제공합니다.
</div>

---

<!-- _class: lead -->

# Summary & Q/A

![bg left:35%](https://images.unsplash.com/photo-1516321318423-f06f85e504b3?w=800)

### Module 01 완료!
* Google Cloud 인터페이스 (Console, CLI, API) 이해
* Cloud Shell 및 개발 환경 기본 사용법 정복

**다음 모듈: 02. 가상 네트워크 (VPC)**
