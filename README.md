## Hi, I'm Shril 👋

**Software Engineer at ADP** — full stack with Java and Spring Boot over Oracle and Postgres, and React on the front end.

Most of what I build sits in the gap between a company signing up for payroll and being approved to actually use it: onboarding, identity verification, and sanctions screening. I built the KYC/CIP platform that gave ADP PEP and beneficial-owner screening it had never run in Canada, and I own three production applications end to end — which mostly means I'm still the person on call for things I shipped a year ago.

---

### 📌 TravelGuide *(in progress)*

**A trip planner that turns forwarded confirmations into a day-by-day plan you can actually follow.** Java 21 · Spring Boot 3 · React 19 · PostgreSQL · AWS + Terraform

A trip lives in eleven places at once — flight in one inbox, hotel in another, car in a PDF, the plan in Notes, and the budget nowhere. TravelGuide is the one place all of it lands.

Three decisions I've committed to and would happily argue about:

- **One schema-constrained LLM call instead of per-vendor parsers.** Confirmation emails across six booking types, three languages, PDF and HTML, into typed and confidence-scored bookings at roughly two cents each. Low-confidence extractions get flagged rather than silently guessed at.
- **Tenant isolation at the data layer, not in app code.** Postgres row-level security instead of scattered app-code checks, with cross-tenant leak tests written before the implementation.
- **Day ordering as an open TSP.** Saved places cluster by geography into day-sized groups; each day solves exactly at ≤7 stops and falls back to 2-opt beyond, under 50 ms.

Building it in the open: repo and spec going public shortly.

---

🔭 &nbsp;**Currently:** going deeper on AWS and system design, and building AI tooling my team uses day to day — an LLM workflow with MCP integrations to Jira, Confluence, and Bitbucket, plus a pre-review agent that catches defects well before code review. Working on a public extension of that pre-review idea next.

🎓 &nbsp;B.S. Computer Science — Rutgers University, New Brunswick.

☕ &nbsp;Outside work: lifting, games, and making coffee I'm probably too particular about.

---

### 🛠 Tech stack

**Languages**

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)

**Backend & Cloud**

![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Spring Security](https://img.shields.io/badge/Spring%20Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white)
![Hibernate](https://img.shields.io/badge/Hibernate-59666C?style=flat-square&logo=hibernate&logoColor=white)
![REST APIs](https://img.shields.io/badge/REST%20APIs-005571?style=flat-square&logo=swagger&logoColor=white)
![OAuth2](https://img.shields.io/badge/OAuth2-EB5424?style=flat-square&logo=auth0&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white)

**Data**

![Oracle](https://img.shields.io/badge/Oracle-F80000?style=flat-square&logo=oracle&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=flat-square&logo=databricks&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)

**Frontend & Tooling**

![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white)
![JUnit](https://img.shields.io/badge/JUnit-25A162?style=flat-square&logo=junit5&logoColor=white)
![Testcontainers](https://img.shields.io/badge/Testcontainers-291A3E?style=flat-square&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![Bitbucket](https://img.shields.io/badge/Bitbucket-0052CC?style=flat-square&logo=bitbucket&logoColor=white)
![MCP](https://img.shields.io/badge/MCP-000000?style=flat-square&logo=anthropic&logoColor=white)

---

### 💬 Things I'm thinking about lately

**Where the transaction ends.** JPA makes a database look like an object graph, and most of the Spring incidents I've chased are that illusion leaking. Such as a @Transactional method calling another one on this so the proxy never fires and the inner boundary doesn't actually exist, a lazy field that's fine in a test and N+1s once it's in a loop, or open-session-in-view holding a connection for as long as serialization takes. The usual fix is mapping entities to DTOs at the service edge so nothing lazy escapes the transaction. It works, and it also means one new field touches four files. I still don't know whether that's the price of a real boundary or ceremony I've gotten used to. If you have a strong opinion there, I'd like to hear it.

**LLMs in developer tooling.** I've shipped MCP integrations and a pre-review agent my team uses daily, so I'm past the demo stage but interested in learning different ways of working or coding to understand the line between tooling that saves reviewers time and tooling that quietly lowers the bar for what gets reviewed properly. If you've built something in this space I'd love to hear how it actually went, even the parts that didn't work.

**How you got where you are.** I enjoy hearing how people ended up doing what they do, especially the parts that weren't planned. If you're further along than me, or earlier and want to compare notes, the inbox is open. No agenda needed.

📫 &nbsp;[patel.shrilk@gmail.com](mailto:patel.shrilk@gmail.com) &nbsp;·&nbsp; [LinkedIn](https://www.linkedin.com/in/shril-patel/)
