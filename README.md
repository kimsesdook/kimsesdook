<!-- 
💡 이 코드를 복사해서 본인의 깃허브 계정명과 동일한 이름의 리포지토리(kimsesdook/kimsesdook)의 README.md 파일에 덮어쓰기 하시면 됩니다! 
-->

<div align="center">

<!-- 타이틀 및 타이핑 효과 애니메이션 -->
<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=26&pause=1000&color=2E86C1&center=true&vCenter=true&width=550&lines=Hi+there!+%F0%9F%91%8B;I'm+Backend+Developer;Focusing+on+Performance+%26+Architecture;Welcome+to+my+GitHub+Profile!" alt="Typing SVG" />

<br/>

<!-- 방문자 수 뱃지 (안정적인 버전) -->
<img src="https://komarev.com/ghpvc/?username=kimsesdook&color=blue&style=flat-square" alt="Profile views" />

</div>

<br/>

## 👨‍💻 About Me

**"단순한 기능 구현을 넘어, 아키텍처의 의도와 성능 최적화를 치열하게 고민하는 개발자입니다."**

저는 **Java**와 **Spring Boot** 생태계를 기반으로 백엔드 시스템을 설계하며, 클라이언트(React)와의 유기적인 데이터 흐름을 이해하는 풀스택 관점을 지향합니다. 단순히 코드를 짜는 것에 그치지 않고, 다음과 같은 기술적 철학을 바탕으로 고품질 소프트웨어를 만듭니다.

* 🌱 **Layered Architecture:** Controller-Service-Repository의 책임을 명확하게 분리하여 유지보수성과 테스트 용이성을 극대화합니다.
* ⚡ **Performance Tuning:** JPA 사용 시 발생하는 `N+1 문제`를 `LEFT JOIN FETCH`를 활용해 능동적으로 해결하며 쿼리 I/O 속도를 튜닝합니다.
* 🛡️ **Security & Validation:** DTO 패턴을 도입해 도메인 엔티티(Entity) 노출을 철저히 막고, 클라이언트 즉각 방어(UX)와 서버 로직(@Valid) 양단에서 **이중 검증 로직**을 구현해 시스템 안정성을 보장합니다.
* 🔭 **현재 활동:** 직장인 웰빙 관리 HR-SaaS 플랫폼 **`CalmDesk`** 고도화 및 **`ClassLink ERP`** 프로젝트 진행 중
* 📫 **Contact:** [이메일 주소 입력] 혹은 [노션/블로그 링크 입력]

<br/>

## 🚀 Pinned Projects & Engineering Experience

제가 시스템 설계 및 개발에 깊게 참여한 주요 프로젝트 및 트러블슈팅 사례입니다.

### 🏢 CalmDesk (HR-SaaS 웰빙 & 근태 관리 시스템)
> **Spring Boot x React 기반 RESTful API 설계 및 서비스 구축**
> * [Backend Repo 바로가기](https://github.com/kimsesdook/CalmdeskBackend) | [Frontend Repo 바로가기](https://github.com/kimsesdook/CallcalmFrontend)

<details open>
<summary><b>👀 핵심 트러블슈팅 및 성과 (클릭해서 접기/펴기)</b></summary>
<br/>

* **JPA N+1 문제 식별 및 쿼리 최적화**  
  단순한 회원 데이터 로드 시 연관된 회사/부서/직급 데이터를 각각 가져올 때 발생하는 서브 쿼리 폭주 현상을 식별했습니다. 이를 해결하기 위해 Spring Data JPA의 `@Query`와 `LEFT JOIN FETCH`를 사용하여 단일 JOIN 쿼리 1개로 최적화, **데이터베이스 I/O 병목 현상을 획기적으로 해결**했습니다.
* **DTO 캡슐화와 시스템 유연성 향상**  
  도메인 엔티티가 프레젠테이션 계층에 직접 노출되는 것을 차단하고, 응답 전용 `ProfileResponse` DTO를 설계했습니다. 이를 통해 사용자 포인트 실시간 연산 로직과 날짜 포맷 로직 등을 캡슐화하여 비즈니스 보안성과 코드 유지보수성을 크게 높였습니다.
* **Axios & Hooks 기반 데이터 사이클 통제**  
  리액트 프론트엔드에서 JWT 토큰 인증과 `useEffect`를 활용해 클라이언트 렌더링 사이클에서 API 통신이 어떻게 일어나는지 완벽히 제어했습니다. 백엔드의 데이터 파이프라인(Controller -> Service -> Repository) 구현뿐만 아니라, JSON 데이터가 프론트 화면에 그려지기까지의 전체 흐름을 주도했습니다.
* **프론트-백엔드 교차 검증(Dual Validation) 적용**  
  클라이언트 사이드에서 불필요한 서버 요청을 줄이는 1차 방어는 물론, Controller 단에 `@Valid`를 적용해 이메일/전화번호 정규식 및 DB 레벨의 중복 체크를 적용하여 악의적인 REST API 요청을 빈틈없이 차단했습니다.
</details>

<br/>

### 📊 ClassLink ERP (전사적 자원 관리 웹 애플리케이션)
> **복잡한 비즈니스 로직의 웹 서비스화**
> * [Repository 바로가기](https://github.com/kimsesdook/ClassLinkErpProject)

<details>
<summary><b>👀 프로젝트 개요 (클릭해서 펴기)</b></summary>
<br/>

* Java, JSP/Servlet을 활용하여 복잡하고 방대한 사내 전사 시스템의 구조를 파악하고, 각 기능별 비즈니스 로직을 효율적이고 유기적인 웹 애플리케이션 기능으로 분리/설계했습니다.
</details>

<br/>

## 🛠️ Tech Stack

> 실무에 직접 부딪혀가며 트러블슈팅을 경험해본 기술들입니다.

### 🍃 Backend & Architecture
<p>
  <img src="https://img.shields.io/badge/Java 17-007396?style=for-the-badge&logo=java&logoColor=white"/> 
  <img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white"/> 
  <img src="https://img.shields.io/badge/Spring_Data_JPA-6DB33F?style=for-the-badge&logo=spring&logoColor=white"/>
  <img src="https://img.shields.io/badge/Hibernate-59666C?style=for-the-badge&logo=Hibernate&logoColor=white"/>
  <img src="https://img.shields.io/badge/Spring_Security-6DB33F?style=for-the-badge&logo=Spring-Security&logoColor=white"/>
  <img src="https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=JSON-web-tokens&logoColor=white"/>
</p>

### 💻 Frontend (Client API Integration)
<p>
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB"/>
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"/>
  <img src="https://img.shields.io/badge/Axios-5A29E4?style=for-the-badge&logo=axios&logoColor=white"/>
</p>

### 🗄️ Database
<p>
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white"/>
  <img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white"/>
</p>

### 🐳 Infrastructure & Tools
<p>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"/>
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white"/>
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white"/>
  <img src="https://img.shields.io/badge/IntelliJ_IDEA-000000?style=for-the-badge&logo=intellij-idea&logoColor=white"/>
</p>

<br/>

## 📈 GitHub Stats

<div align="center">
  
  <p>
    <!-- 트로피 애니메이션 추가 -->
    <a href="https://github.com/ryo-ma/github-profile-trophy">
      <img src="https://github-profile-trophy.vercel.app/?username=kimsesdook&theme=flat&no-frame=true&no-bg=true&margin-w=15" alt="kimsesdook" />
    </a>
  </p>

  <br/>

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
