<h1 align="center">Hi 🤓, I'm Sachin Lakshitha</h1>

<h2 align="center"> I build stuff! </h2>
- I’m currently working on understanding LLVM:InstCombine / InstSimplify / ValueTracking , transforms module and an Orderbook that parses NASDAQ in C++ and simulates real market data. 
  

-  I’m currently learning **LLVM,C++ and a bit of devops/infra**
-  Learning C++ and performance related concepts trying to understand memory, concurrency, cache, hardware behaviour and operating systems.
-  My code looks super c-ish even though i do use new features.. maybe because it doesn't have enough colons! i do try to follow misra and google style guides for cpp.
-  I will build things that are solved already to understand them and hopefully someday help the people that maintain these systems!
-  Looking towards a compiler/ Hpc career or SRE/Devops.

  
i like to build like a lotttttttttttttt.like a whole looott
and i read code like a lott. like all the time.

tool dump incoming (ik)

## **Languages and Tools I'm Familiar With**

### ⚙️ Systems 
![C++](https://img.shields.io/badge/-C++-00599C?style=flat-square&logo=c%2B%2B)
![C](https://img.shields.io/badge/-C-A8B9CC?style=flat-square&logo=c&logoColor=black)
![CMake](https://img.shields.io/badge/-CMake-064F8C?style=flat-square&logo=cmake&logoColor=white)
![MSVC](https://img.shields.io/badge/-MSVC-5C2D91?style=flat-square&logo=visual-studio&logoColor=white)
![Linux](https://img.shields.io/badge/-Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![GDB](https://img.shields.io/badge/-GDB-A8B9CC?style=flat-square&logo=gnu&logoColor=black)


### **Frontend Development**
![HTML5](https://img.shields.io/badge/-HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/-CSS3-1572B6?style=flat-square&logo=css3)
![JavaScript](https://img.shields.io/badge/-JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/-React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Next.js](https://img.shields.io/badge/-Next.js-000000?style=flat-square&logo=next.js&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/-Tailwind_CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)

### **Backend Development**
![Node.js](https://img.shields.io/badge/-Node.js-339933?style=flat-square&logo=node.js&logoColor=white)
![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/-FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![PHP](https://img.shields.io/badge/-PHP-777BB4?style=flat-square&logo=php&logoColor=white)
![Java](https://img.shields.io/badge/-Java-007396?style=flat-square&logo=java)


### **Databases**
![MongoDB](https://img.shields.io/badge/-MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-336791?style=flat-square&logo=postgresql)
![MySQL](https://img.shields.io/badge/-MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![SQLite](https://img.shields.io/badge/-SQLite-003B57?style=flat-square&logo=sqlite)
![Supabase](https://img.shields.io/badge/-Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white)

### **Development Tools**
![Git](https://img.shields.io/badge/-Git-F05032?style=flat-square&logo=git&logoColor=white)
![Postman](https://img.shields.io/badge/-Postman-FF6C37?style=flat-square&logo=postman&logoColor=white)
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white)


### **Additional tools**
- **UI Libraries**: mainly Material,redux and shadcn
- **API Development**:  RESTful APIs with FastAPI, Express and Spring
- **Data Validation**: Zod, Pydantic
- **UI/visualization**: matplotlib 
---



Projects!!!

## HFT Backtesting Engine — C++(high performance/low latency software)
- Reads real NASDAQ market data and reconstructs a live orderbook from raw bytes. You can run your own trading strategy against it and see if it makes money. A built-in market maker using the Avellaneda-Stoikov model backtested across 100 symbols  including high-volatility sessions — came out ~$15k simulated PnL, with accurate fill simulation down to queue position and depth.
- The PnL isn't the point.
- The point is what had to be built to get there: parsing NASDAQ ITCH 5.0 binary protocol at the byte level, reconstructing the full L3 orderbook, then building the infrastructure underneath it — lock-free SPSC/MPSC queues, memory pools with aligned prefaulted allocation, hierarchical bitsets with compiler intrinsics for fast lookups, cache-line aware data layout, RAII ownership throughout.
- And also learned tooling like ASan,TSan and GDB. works for both GCC and MSVC.
- It's a working answer to the question: what does it actually take to keep the prefetcher, cache, TLB, and CPU happy from raw bytes all the way to PnL?

## it is a fun journey! changed the entire way of how i view software and made the hardware visible to me!

## Royal Beverages — Vanilla PHP E-Commerce - (full stack but i built a mini framework)
- Built to understand what Laravel and React actually do.
- No frameworks. Custom MVC from scratch, reflection-based DI container that autowires classes automatically, regex router, framework-less SPA renderer for the admin dashboard, PSR-4 autoloader, multi-warehouse FIFO stock engine with row-level locking.
- The interesting part isn't the storefront. It's that once you've written your own DI container, you stop treating Laravel's service container as magic. Same with the router. Same with the SPA renderer. That's why this exists.
- Full technical breakdown in ARCHITECTURE.md. Docker setup in two commands.

## DevOps Learning Platform — TypeScript / Go - (addressing the issue where existing devops onboarding seems to miss the painpoints)
- KodeKloud exists. This is different.
- Most platforms give you a sandbox and a checklist. This one drops you into a broken system and asks you to fix it — the way you'd actually encounter it at work. 
- The platform itself is the curriculum: the same Kafka, Kubernetes, Postgres RLS, and observability stack you're learning about is what's running underneath you. I will try to encode as much pain points as i can in real development!
- The hard part isn't the feature set. It's that running user code safely at scale is an unsolved problem in this codebase.Firecracker is the likely answer. The current approach: Kafka dispatches sandbox jobs to a Go worker, the goroutine spawns the container then drops ownership, stdio path returns immediately. State lives in Redis, async-written to Postgres. It's hybrid and it's honest about being hybrid.
- Architecture decisions are documented in docs/adr — including what was chosen, what was rejected, and what will break under load.


## Bookfair Stall Reservation System — React / Spring Boot / Java - (full stack)
- The interesting problem wasn't the reservations. It was the floor plan designer.
- Admins draw stalls directly onto a canvas. Influence zones — traffic hotspots, entrances, food courts — radiate outward as circles and adjust stall prices based on proximity, geometry, and edge distance. Move a stall closer to an entrance and the price updates in real time. The pricing heuristic isn't a lookup table; it's a spatial calculation that runs on every geometry change.
Under that: three canvas layers (zones, influences, stalls) with separate draw modes and interaction semantics, SELECT FOR UPDATE row locking to prevent double-booking under concurrent load, STOMP WebSocket broadcast so every connected client sees reservation changes sub-100ms, and a full CI/CD pipeline deploying to EC2 via GitHub Actions.
- The state architecture for the designer alone — separating raw mouse lifecycle from domain state from interaction context — took longer to get right than most of the rest of the system.
- Technical deep-dive in architecture.md. Docker up in one command.




