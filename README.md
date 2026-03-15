
<div align="center">

<!-- 타이틀 및 타이핑 효과 애니메이션 -->
<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=26&pause=1000&color=2E86C1&center=true&vCenter=true&width=580&lines=Hi+there!+%F0%9F%91%8B;I'm+Backend+Developer;Focusing+on+Data+Flow+%26+Validation;Welcome+to+my+GitHub+Profile!" alt="Typing SVG" />

<br/>

<!-- 방문자 수 뱃지 (안정적인 버전) -->
<img src="https://komarev.com/ghpvc/?username=kimsesdook&color=blue&style=flat-square" alt="Profile views" />

</div>

<br/>

## 👨‍💻 About Me

**"단일 애플리케이션 안의 데이터 파이프라인(React ↔ Spring Boot) 구축과 안정성을 고민하는 개발자입니다."**

저는 **Java**와 **Spring Boot** 생태계를 기반으로 백엔드 시스템을 설계하지만, 클라이언트(React)와의 유기적인 데이터 흐름의 중요성을 잘 이해하고 있습니다. 특히 다음과 같은 기술적 철학을 바탕으로 고품질 소프트웨어를 만듭니다.

* 🌱 **Layered Architecture:** Controller-Service-Repository의 책임을 명확하게 분리하여 유지보수성과 테스트 용이성을 극대화합니다.
* ⚡ **Data Flow Control:** 백엔드에서 캡슐화한 데이터를 DTO로 변환하여 뿌려주고, 이를 클라이언트의 상태 관리(useState, useEffect)와 완벽히 융합시킵니다.
* 🛡️ **Cross Validation:** 프론트엔드(UX)를 위한 즉각적인 방어와 백엔드(@Valid, DB 단위 검증)를 활용한 이중 보안 검사 체계를 구축합니다.
* 🔭 **현재 활동:** 직장인 웰빙 관리 HR-SaaS 플랫폼 **`CalmDesk`** 백엔드/프론트엔드 고도화
* 📫 **Contact:** [kimsesdook@gmail.com] 혹은 [노션/블로그 링크 입력]

<br/>

## 🚀 Pinned Projects & Engineering Experience

제가 시스템 설계부터 풀스택 연동까지 깊게 참여한 핵심 프로젝트와 트러블슈팅 사례입니다.

### 🏢 CalmDesk (HR-SaaS 웰빙 & 근태 관리 시스템)
> **상담원의 스트레스를 관리하는 HR-SaaS**
> * [Backend Repo](https://github.com/kimsesdook/CalmdeskBackend) | [Frontend Repo](https://github.com/kimsesdook/CallcalmFrontend)

<details open>
<summary><b>👀 핵심 트러블슈팅 및 기술적 성과 (클릭해서 접기/펴기)</b></summary>
<br/>

* **욕설 감지 시스템 서버 부하 및 외부 의존성 문제 해결**
  * **Issue**: 기존에 STT 기반 텍스트를 외부 API(Spring AI)에 전송하여 욕설을 판단하던 구조에서 통화 1건당 응답 지연과 비용이 누적되고, AI의 비결정성(결과의 불일치) 문제에 직면했습니다.
  * **Solve**: 외부 API 통신 대신 DB 기반의 욕설 사전(`profanity_word`) 직접 매칭 방식으로 전면 리팩토링했습니다.
  * **Result**: DB 부하를 막기 위해 **1분 TTL 인메모리 캐시를 도입**하고, 운영 중 실시간 관리를 위한 `active` 상태 컬럼을 설계했습니다. 획기적인 응답 속도 단축 및 100% 결과의 일관성을 확보했습니다.
* **JPA N+1 문제 해결 및 쿼리 최적화 (응답속도 1,200ms → 150ms)**
  * **Issue**: 관리자용 휴가 목록 조회 시 회원, 기업, 부서 엔티티가 지연 로딩(LAZY)되면서 요청 1번에 101회의 조회가 폭주하는 쿼리 병목(N+1)을 확인했습니다.
  * **Solve**: Spring Data JPA의 `@Query` 내부 `LEFT JOIN FETCH`를 적용하여 단 한 번의 조인 쿼리로 연관 데이터를 즉시 가져오도록 리팩토링했습니다.
  * **Result**: 불필요한 IO 병목을 완전히 제거하여 API 응답 시간을 평균 **1,200ms에서 150ms로 단축**, 상황에 맞는 유동적 Fetch Join 제어의 중요성을 실감했습니다.
</details>

<br/>

### 📊 ClassLink ERP (전사적 자원 관리 웹 애플리케이션)
> **웹 서비스화 로직 세분화 및 데이터 무결성 확보**
> * [Repository 바로가기](https://github.com/kimsesdook/ClassLinkErpProject)

<details open>
<summary><b>👀 핵심 트러블슈팅 및 기술적 성과 (클릭해서 접기/펴기)</b></summary>
<br/>

* **재고 관리 로직 내 동시 승인 시 데이터 음수 무결성 파괴 방어**
  * **Issue**: 관리자가 여러 개의 기자재 대여를 승인할 때, 잔여 재고보다 많은 대량 요청이 승인되어 재고가 마이너스(-) 숫자로 표기되는 심각한 데이터 정합성 오류를 발견했습니다.
  * **Solve**: 트랜잭션 도중 상태값만 무작정 업데이트하는 기존 방식에서 탈피하여, `FacilityService` 승인 진입 시퀀스에 **현재 남은 수량(잔여 재고)을 사전 검증하는 선행 방어 로직**을 새롭게 구현했습니다.
  * **Result**: 재고가 모자란 초과 요청은 곧바로 직관적인 응답 코드(실패: 0 / 성공: 1)로 반환토록 리팩토링하여, 백엔드 데이터의 **100% 무결성을 확보함과 동시**에 클라이언트(프론트엔드)에서 즉각 Alert 메시지를 띄우는 UX 향상을 이끌어 냈습니다.
</details>

<br/>

## 🛠️ Tech Stack

### 🍃 Backend & Data
<p>
  <img src="https://img.shields.io/badge/Java-007396?style=for-the-badge&logo=java&logoColor=white"/> 
  <img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white"/> 
  <img src="https://img.shields.io/badge/Spring-6DB33F?style=for-the-badge&logo=spring&logoColor=white"/> 
  <img src="https://img.shields.io/badge/JPA-59666C?style=for-the-badge&logo=hibernate&logoColor=white"/>
  <img src="https://img.shields.io/badge/MyBatis-000000?style=for-the-badge&logoColor=white"/>
  <img src="https://img.shields.io/badge/JSP%2FServlet-007396?style=for-the-badge&logo=java&logoColor=white"/>
  <br/>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/AWS_Lambda-FF9900?style=for-the-badge&logo=aws-lambda&logoColor=white"/>
  <img src="https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logoColor=white"/>
  <img src="https://img.shields.io/badge/Oracle-F00000?style=for-the-badge&logo=oracle&logoColor=white"/>
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white"/>
</p>

### 💻 Client & Tools
<p>
  <img src="https://img.shields.io/badge/HTML5_%26_CSS3-E34F26?style=for-the-badge&logo=html5&logoColor=white"/>
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB"/>
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"/>
  <img src="https://img.shields.io/badge/AJAX-005571?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white"/>
  <br/>
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white"/>
  <img src="https://img.shields.io/badge/REST_API-005571?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Slack-4A154B?style=for-the-badge&logo=slack&logoColor=white"/>
</p>

<br/>

## 📈 GitHub Stats

<div align="center">
  <!-- 이미지 레이아웃이 깨지던 원인인 트로피 뱃지(Broken Link)는 완전히 제거하여 레이아웃을 깔끔하게 복구했습니다. -->

  <p>
    <!-- 깃허브 전체 Stats & 많이 쓰는 언어 -->
    <img src="https://github-readme-stats.vercel.app/api?username=kimsesdook&show_icons=true&theme=buefy&hide_border=true&title_color=2E86C1" height="150px" alt="stats" />
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=kimsesdook&layout=compact&theme=buefy&hide_border=true&title_color=2E86C1" height="150px" alt="top langs" />
  </p>
  
  <p>
    <!-- 연속 커밋(스트릭) 통계 -->
    <img src="https://github-readme-streak-stats.herokuapp.com/?user=kimsesdook&theme=buefy&hide_border=true&stroke=0000&title_color=2E86C1" alt="GitHub Streak" />
  </p>

</div>

---

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=auto&height=100&section=footer&text=Thank%20You%20For%20Visiting!&fontSize=30&fontAlignY=50&descAlignY=61&descAlign=62" width="100%"/>
</div>
