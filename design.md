# GreenMetrix AI (GM) – System Design Document

## 1. Introduction
GreenMetrix AI (GM) is a scalable digital circular economy platform that enables waste pickup, segregation, tracking, recycling marketplace matching, and transformation of waste into reusable infrastructure products.

Phase-1 focuses on plastic waste conversion into bricks/tiles/blocks.
Future expansion includes food waste composting, paper recycling, e-waste recycling, and carbon credit tracking.

---

## 2. System Architecture Overview
GreenMetrix AI is designed with modular components to support scalability and future integration.

### Major Components
1. Web/Mobile Frontend Interfaces
2. Backend API Gateway
3. AI Classification & Recommendation Engine
4. Scheduling & Routing Optimization Engine
5. Marketplace & Transaction Module
6. Rewards & Gamification Module
7. CSR Reporting & Impact Analytics Engine
8. Database & Storage Layer

---

## 3. Architecture Diagram (Text)

[ Users: Generator / Collector / Recycler / CSR / Admin ]
                     |
                     v
           [ Web + Mobile Frontend ]
                     |
                     v
           [ Backend API Gateway ]
     |         |         |         |
     v         v         v         v
[Auth]   [Pickup & Route] [Marketplace] [Rewards]
     |         |         |         |
     v         v         v         v
           [ Database & Storage ]
                     |
                     v
               [ AI Engine ]
         (Classification + Scoring + Suggestions)

External Integrations:
- Maps API (routing)
- QR Generator
- SMS/WhatsApp Notifications
- Email Reporting

---

## 4. Suggested Tech Stack

### Frontend
- React.js (dashboard)
- Flutter / React Native (mobile)

### Backend
- Python FastAPI / Node.js Express

### Database
- PostgreSQL (structured tracking and users)
- Optional MongoDB (metadata)
- Object Storage (S3) for image uploads

### AI Layer
- TensorFlow/PyTorch for waste classification model
- OpenCV for preprocessing
- LLM-based segregation assistant (optional)

### Deployment
- AWS EC2 / AWS Lambda
- AWS S3 storage
- AWS RDS PostgreSQL
- GitHub for repository management

---

## 5. Module Design

## 5.1 Authentication & Role Management
- OTP login
- RBAC access control
- Verification workflow for collectors and recyclers

---

## 5.2 Pickup Request Management
### Workflow
1. Generator creates request
2. AI classifies waste (optional)
3. System schedules pickup
4. Collector accepts and completes pickup
5. Batch created with QR code

---

## 5.3 AI Waste Classification Module
### Input
- uploaded waste image

### Output
- waste type prediction
- recyclability score (0–100)
- segregation recommendation text

Model approach:
- CNN-based image classifier
- rule-based scoring engine

---

## 5.4 Scheduling & Route Optimization
Assignment parameters:
- distance proximity
- time-slot availability
- vehicle capacity
- waste compatibility

Routing:
- shortest path routing using Maps API
- multi-stop optimized pickup plan

---

## 5.5 Batch Tracking & QR Traceability
Batch lifecycle:
Pickup Request → Waste Batch → Recycler Processing → Product Output

Each batch stores:
- batch ID
- QR code
- timestamps
- handler logs (collector/recycler)

This ensures auditability for CSR and government verification.

---

## 5.6 Marketplace Module
Recyclers can:
- view available batches
- accept or bid for waste supply
- maintain ratings and reliability score

Marketplace improves:
- supply chain predictability
- recycling unit productivity
- reduced waste leakage

---

## 5.7 Processing & Output Module
Recycler updates:
- input weight
- processing method
- output product quantity
- residue percentage

System calculates:
- conversion ratio
- CO₂ saved estimate
- efficiency score

---

## 5.8 CSR Impact Analytics
CSR module generates:
- campaign-wise report
- region-wise waste diversion metrics
- verified recycling certificates

Verification inputs:
- batch QR logs
- recycler proof uploads
- NGO validation (future)

---

## 5.9 Rewards & Gamification
Users earn points based on:
- segregation quality score
- pickup frequency
- waste quantity

Gamification features:
- badges
- community leaderboard
- redeemable credits

---

## 6. Database Schema (High Level)

### Users
- user_id (PK)
- name
- phone
- role
- city
- created_at

### PickupRequests
- request_id (PK)
- generator_id (FK)
- waste_type
- estimated_weight
- pickup_address
- status
- image_url
- created_at

### CollectorAssignments
- assignment_id (PK)
- request_id (FK)
- collector_id (FK)
- status
- assigned_at

### WasteBatches
- batch_id (PK)
- request_id (FK)
- collector_id (FK)
- waste_type
- actual_weight
- qr_code
- status
- timestamp

### RecyclerProcessing
- process_id (PK)
- batch_id (FK)
- recycler_id (FK)
- processing_type
- output_type
- output_quantity
- conversion_ratio
- completed_at

### CSRReports
- report_id (PK)
- sponsor_id
- region
- total_waste_recycled
- total_co2_saved
- generated_at

### Rewards
- reward_id (PK)
- user_id (FK)
- points
- badge_level
- redeemed_status

---

## 7. API Design (Sample)

### Auth
POST /api/auth/register  
POST /api/auth/login  
POST /api/auth/verify  

### Pickup
POST /api/pickup/create  
GET /api/pickup/my-requests  
PUT /api/pickup/update-status  

### AI
POST /api/ai/classify-waste  

### Collector
GET /api/collector/assigned  
POST /api/collector/complete  

### Recycler
GET /api/recycler/batches  
POST /api/recycler/accept  
POST /api/recycler/process-update  

### CSR
GET /api/csr/dashboard  
GET /api/csr/report  

---

## 8. User Journey

### Generator Journey
Upload waste photo → AI suggests segregation → create pickup request → pickup completed → points credited

### Collector Journey
Receive assigned pickups → follow optimized route → pickup confirmation → QR batch generation → delivery

### Recycler Journey
Accept batch → process waste → update output → generate product traceability QR

### CSR Journey
Fund initiative → track impact dashboard → download verified report

---

## 9. Security & Compliance
- RBAC-based authorization
- secure storage of batch evidence
- QR traceability for audit
- collector and recycler verification process

---

## 10. Prototype Deployment Plan
- Frontend: Vercel / Netlify
- Backend: AWS EC2 / Render
- Database: AWS RDS PostgreSQL
- AI model: hosted service or integrated API

---

## 11. Future Roadmap
Phase-2: Food waste compost + paper recycling  
Phase-3: E-waste + metal waste + recycling automation  
Phase-4: Blockchain proof + carbon credit marketplace  
Phase-5: National circular economy dashboard for Bharat

---

## 12. Conclusion
GreenMetrix AI (GM) provides a structured, AI-powered circular economy ecosystem for Bharat by connecting waste generators, collectors, recyclers, and CSR sponsors. The platform ensures waste traceability, optimized logistics, and verified recycling output, enabling measurable sustainability impact at scale.

