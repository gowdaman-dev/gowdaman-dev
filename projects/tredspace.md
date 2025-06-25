# 💹 TradeScan - Real-Time Trading Analytics Platform

[![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![React](https://img.shields.io/badge/React-61DAFB?logo=react&logoColor=black)](https://reactjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-339933?logo=node.js)](https://nodejs.org/)
[![Redis](https://img.shields.io/badge/Redis-DC382D?logo=redis)](https://redis.io/)
[![Microservices](https://img.shields.io/badge/Architecture-Microservices-2496ED?logo=docker)](https://microservices.io/)

**A scalable SaaS platform for traders to share market insights with real-time updates.**  
Developed key modules as a freelance full-stack developer using TypeScript, Redis Pub/Sub, and Socket.IO.

➡️ **Demo:** [tradescan.app](https://tradescan.app) | **Client:** TredStock.ai  
➡️ **My Role:** Built TradeSpace (primary) and Resources (secondary) modules

---

## 🎯 Key Features I Implemented

### 📊 **TradeSpace Module** (Primary Contribution)
- **Real-time trade publishing** with Socket.IO and Redis event pipelines
- **Admin announcement system** with role-based permissions (JWT)
- **Tag-based filtering** for market data analysis
- Optimized WebSocket message batching for **500+ concurrent users**

### 📚 **Resources Module** (Secondary Contribution)
- Curated knowledge base with **role-based access control**
- Redis-backed content synchronization
- Searchable interface with lazy-loaded assets

---

## 🛠 Tech Stack Deep Dive

| Layer           | My Implementation Details                     |
|-----------------|-----------------------------------------------|
| **Frontend**    | React + TypeScript, Tailwind CSS, Socket.IO client |
| **Backend**     | Express.js (TypeScript), Redis Pub/Sub        |
| **Real-Time**   | Socket.IO rooms, Redis event pipelining       |
| **Auth**        | JWT with role claims, API Gateway enforcement |
| **DevOps**      | Dockerized microservices, CI/CD ready         |

---

## 🏗 Architecture (My Implementation)

```mermaid
graph LR
    A[React Client] -->|API Calls| B[API Gateway]
    B --> C[TradeSpace Microservice]
    B --> D[Resources Microservice]
    C -->|trade:posted| E[(Redis Pub/Sub)]
    D -->|resource:updated| E
    E --> F[Socket.IO Server]
    F -->|Live Updates| A
