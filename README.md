<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=Rounded&color=FAEF9B&height=300&section=header&text=Hokyun's%20GitHub&fontSize=90" alt="header" width="100%"/>
</div>

<div align="center">

### 다양한 개발경험을 중요시하는 개발자
AI시대에 하나의 기술을 집중하는 것도 중요하지만 다양한 기술을 접하는 것 역시 중요하다고 생각합니다.<br/>
기술을 접할 때마다 수박 겉핡기가 아닌, 기술의 원리와 설계의도를 파악하며 개발합니다.

</div>

---

## 👋 About Me

- 🎯 **Spring Boot / Django** 기반 백엔드 개발을 중심으로 합니다.
- 📱 개인 서비스 **Leave**를 기획부터 배포·운영까지 진행했습니다. (Flutter 앱 + Spring Boot API + AWS 인프라)
- 🔐 **JWT 기반 인증**을 여러 프로젝트에서 반복 구현하며, 토큰 만료·재발급·권한 검증 설계를 다뤘습니다.
- 📊 금융 데이터 분석 공모전에서 **데이터 수집 파이프라인**과 **국가 간 상관분석**을 담당했습니다.
- ✍️ 잘한 것뿐 아니라 **한계와 개선점도 문서로 남기는 것**을 기준으로 합니다.

---

## 🚀 Projects

| 프로젝트 | 한 줄 소개 | 역할 | 핵심 기술 |
|---|---|:---:|---|
| **[🏖️ Leave](https://github.com/hokyun-tazo/Leave)** | 개인 연차 관리 앱 — **실서비스 배포 · 운영** | 1인 개발 | `Flutter` `Spring Boot 3` `Java 21` `PostgreSQL` `Docker` `Nginx` `GitHub Actions` |
| **[🎧 ODI](https://github.com/hokyun-tazo/OD)** | 사용자 맞춤 음성 오디오북 플랫폼 | Backend | `Django 5` `DRF` `PostgreSQL` `AWS(EC2·S3·RDS)` `OAuth2` `JWT` `TTS·RVC` |
| **[📈 NH 빅데이터 경진대회](https://github.com/hokyun-tazo/NH_Competition)** | 한·미·중 섹터 주가 상관관계 분석 | 데이터 수집 · 중국 분석 | `Python` `pandas` `SciPy` `BeautifulSoup` `yfinance` |
| **[🏠 Togethers](https://github.com/hokyun-tazo/CapStone_NSU)** | 룸메이트 매칭 플랫폼 (캡스톤 디자인) | Backend | `Spring Boot 2.7` `JPA` `MySQL` `Thymeleaf` `JWT` `WebSocket` |

<br/>

### 🏖️ Leave — 개인 연차 관리 앱

> **기획 · 디자인 · 프론트 · 백엔드 · 인프라를 혼자 맡아, 실제 도메인과 앱 배포까지 완료한 서비스입니다.**

- **단순 CRUD를 넘어선 도메인 로직** — 연차/반차/반반차 **가중치 집계**, 주말·공휴일 자동 제외, 잔여 연차 사전 검증
- **성능을 고려한 쿼리 설계** — `LEAD()`/`LAG()` 윈도우 함수로 데이터와 이전/다음 존재 여부를 **단일 쿼리**로 조회
- **공휴일 자동 동기화 배치** — 공공데이터포털 API 연동, 월 단위 예외 격리 + **멱등성** 확보
- **무인 운영 인프라** — Docker Compose + Nginx(HTTPS) + GitHub Actions Self-hosted Runner **자동 배포**
- **테스트 26개** 작성 (서비스 계층 통합 테스트)
- 📌 약 3개월 운영 후, **수익 구조의 한계를 지표로 판단해 서비스를 종료**했습니다. 

### 🎧 ODI — 사용자 맞춤 음성 오디오북

> **내가 원하는 목소리로 책을 듣는다** — AI 음성 학습과 오디오북을 결합한 플랫폼의 백엔드를 담당했습니다.

- **소셜 로그인 → 자체 JWT** — Google · Kakao OAuth2 인가 코드 흐름을 **자체 토큰 체계로 통합**, 미들웨어에서 전역 검증
- **AI 파이프라인 설계** — 학습(비실시간)과 변환(실시간)을 분리하고 모델은 S3, 메타데이터는 RDS로 나눠 **재생 지연 최소화**
- **동시성 처리** — 도서 신청 집계에 `F()` 표현식 + 트랜잭션을 적용해 **DB 레벨 원자적 증가**
- **비동기 메일 발송** — 외부 SMTP 응답을 기다리지 않도록 별도 스레드로 분리

### 📈 NH 빅데이터 경진대회 — 한·미·중 섹터 상관분석

> **데이터 수집 전반**과 **중국 데이터 분석**을 담당했습니다.

- **8개 소스 통합** — NH 제공 CSV + SPDR 섹터 API + TradingView 크롤링 + 금융 API + 거시지표(환율·금리·유가·성장률)
- **서로 다른 주기의 데이터 정렬** — 영업일/월/연 단위 지표를 일 단위로 리샘플링, 3국 공통 개장일만 추출
- **중국 데이터 수집 자동화** — 거래소 코드를 파싱해 `.SS`/`.SZ` 접미사 자동 변환, 섹터 URL만 바꾸면 재사용 가능한 구조
- **결과** — 한국 기술주는 미국과 **+0.93** 동조, 중국과는 **−0.44** 역상관. 필수소비재는 미·중 모두와 음의 상관

---

## 🛠 Tech Stack

**Backend**

<span>
    <img src="https://img.shields.io/badge/Java-6DA4AA?style=plastic&logo=openjdk&logoColor=white"/>
    <img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=plastic&logo=springboot&logoColor=white"/>
    <img src="https://img.shields.io/badge/Spring%20Security-6DB33F?style=plastic&logo=springsecurity&logoColor=white"/>
    <img src="https://img.shields.io/badge/JPA%20/%20Hibernate-59666C?style=plastic&logo=hibernate&logoColor=white"/>
    <img src="https://img.shields.io/badge/Python-3776AB?style=plastic&logo=Python&logoColor=white"/>
    <img src="https://img.shields.io/badge/Django-092E20?style=plastic&logo=Django&logoColor=white"/>
    <img src="https://img.shields.io/badge/DRF-A30000?style=plastic&logo=django&logoColor=white"/>
    <img src="https://img.shields.io/badge/JWT-000000?style=plastic&logo=jsonwebtokens&logoColor=white"/>
</span>

**Database**

<span>
    <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=plastic&logo=postgresql&logoColor=white"/>
    <img src="https://img.shields.io/badge/MySQL-4479A1?style=plastic&logo=MYSQL&logoColor=white"/>
</span>

**Frontend / App**

<span>
    <img src="https://img.shields.io/badge/Flutter-02569B?style=plastic&logo=flutter&logoColor=white"/>
    <img src="https://img.shields.io/badge/Dart-0175C2?style=plastic&logo=dart&logoColor=white"/>
    <img src="https://img.shields.io/badge/Thymeleaf-005F0F?style=plastic&logo=thymeleaf&logoColor=white"/>
</span>

**Infra / DevOps**

<span>
    <img src="https://img.shields.io/badge/Docker-2496ED?style=plastic&logo=docker&logoColor=white"/>
    <img src="https://img.shields.io/badge/Nginx-009639?style=plastic&logo=nginx&logoColor=white"/>
    <img src="https://img.shields.io/badge/AWS-232F3E?style=plastic&logo=amazonaws&logoColor=white"/>
    <img src="https://img.shields.io/badge/GitHub%20Actions-2088FF?style=plastic&logo=githubactions&logoColor=white"/>
    <img src="https://img.shields.io/badge/Google%20Cloud-4285F4?style=plastic&logo=googlecloud&logoColor=white"/>
</span>

**Data**

<span>
    <img src="https://img.shields.io/badge/pandas-150458?style=plastic&logo=pandas&logoColor=white"/>
    <img src="https://img.shields.io/badge/NumPy-013243?style=plastic&logo=numpy&logoColor=white"/>
    <img src="https://img.shields.io/badge/SciPy-8CAAE6?style=plastic&logo=scipy&logoColor=white"/>
    <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=plastic&logo=Tensorflow&logoColor=white"/>
</span>

**Collaboration**

<span>
    <img src="https://img.shields.io/badge/Git-F05032?style=plastic&logo=git&logoColor=white"/>
    <img src="https://img.shields.io/badge/GitHub-181717?style=plastic&logo=github&logoColor=white"/>
    <img src="https://img.shields.io/badge/Jira-0052CC?style=plastic&logo=jira&logoColor=white"/>
</span>



## 📫 Contact

<span>
    <a href="mailto:wjdghrbs2468@naver.com">
        <img src="https://img.shields.io/badge/wjdghrbs2468@naver.com-03C75A?style=plastic&logo=naver&logoColor=white"/>
    </a>
</span>
