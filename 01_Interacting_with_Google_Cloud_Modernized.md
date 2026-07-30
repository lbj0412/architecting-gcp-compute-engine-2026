# Google Compute Engine 아키텍팅 (2026 최신 개정판)
## 모듈 01: Google Cloud와 상호작용 (Interacting with Google Cloud) - 발표 및 교재용 개정본

> **문서 개요**: 본 문서는 `01_Interacting_with_Google_Cloud_KO.pdf` (20장)를 바탕으로 2026년 최신 Google Cloud 관리 도구(Console, Cloud Shell, SDK, REST API, Mobile App) 및 베스핀글로벌 실습 가이드와 보안/비용 규격을 100% 한글로 재구성한 개정 교재입니다.

---

## 📌 목차
1. **Google Cloud 상호작용 4가지 주요 방법**
2. **Google Cloud Console, Cloud SDK, Cloud Shell 상세 비교**
3. **콘솔 탐색 메뉴 및 VM 인스턴스 페이지 제어**
4. **RESTful APIs, Client Libraries 및 OAuth 2.0 보안 인증**
5. **Cloud Mobile App을 활용한 모니터링 및 긴급 장애 조치**
6. **베스핀글로벌 실습 01: 콘솔 및 Cloud Shell 스토리치 제어**
7. **베스핀글로벌 실습 02: Google Cloud Marketplace 1-Click 자동 배포**
8. **실습 필수 보안 & 비용(FinOps) 관리 규격**
9. **모듈 01 복습 퀴즈 1 & 퀴즈 2 (정답 및 상세 해설)**

---

## 01. Google Cloud 상호작용 4가지 주요 방법

### 🖥️ 1. Google Cloud Console (`console.cloud.google.com`)
* 웹 브라우저 기반의 직관적인 GUI 관리 화면
* 마우스 클릭을 통한 리소스 상태 조회, 생성, 중지 및 설정 관리

### 💻 2. Cloud Shell & Cloud SDK
* `gcloud`, `gsutil`, `bq` 명령어 기반 CLI 터미널 인터페이스
* **Cloud Shell**: 로컬 PC 설치 없이 구글 브라우저 안에서 **5GB 영구 무료 디렉토리**를 제공하는 Linux VM 터미널

### ⚡ 3. REST-based APIs & Client Libraries
* HTTP RESTful 메서드(GET, POST, PUT, DELETE) 및 JSON 포맷 기반 인프라 제어
* Java, Python, Node.js, Go, Ruby 등 최적화된 Client Libraries 및 OAuth 2.0 보안 토큰 인증

### 📱 4. Cloud Mobile App
* Android 및 iOS 스마트폰 전용 관리 애플리케이션
* 이동 중 알림(Alert) 수신, 실시간 CPU/네트워크 그래프 모니터링, SSH 접속 및 VM 긴급 전원 제어

---

## 02. 실습 및 보안/비용(FinOps) 핵심 규격

### 🏢 베스핀글로벌 GCP 실습 환경
* **조직**: `bespin.email`
* **프로젝트**: `KDT5T`
* Qwiklabs 미사용 (부여된 계정으로 Console 로그인 후 `KDT5T` 프로젝트 내에서 실습 진행)

### 🚨 보안 엄금 수칙
* **Service Account Key JSON 파일 및 API Key는 절대로 Public망이나 GitHub 공용 저장소에 업로드 금지!**
* 노출 시 봇(Bot) 해킹으로 인해 수천만 원 상당의 비용 청구 폭탄 발생 위험.

### ⚠️ 비용(FinOps) 수칙
* 수업 종료 및 쉬는 시간 실습 미진행 시 **Compute Engine VM 전원을 반드시 OFF(중지)** 조치.
* GCP 요금 집계 데이터는 **최소 2일(48시간) 시차**가 존재함을 상시 인지.
