# GreenMetrix AI (GM) – Requirements Specification

## 1. Project Overview
GreenMetrix AI (GM) is an AI-powered circular economy platform designed to help Bharat convert waste into measurable economic value by enabling seamless coordination between waste generators, collectors, recyclers, manufacturers, CSR sponsors, and municipalities.

The platform provides end-to-end waste traceability, optimized pickup scheduling, AI-based waste classification, incentive-based participation, and transformation of waste into reusable products such as plastic bricks/tiles, compost, recycled pellets, and other industrial inputs.

Phase-1 prototype focuses on plastic waste conversion into construction materials (tiles, bricks, blocks), while the long-term roadmap supports multiple waste streams (plastic, food, paper, metal, e-waste).

---

## 2. Problem Statement
India generates millions of tons of waste annually, but the recycling ecosystem remains fragmented. Major challenges include:
- low segregation at source
- lack of traceability across waste collection chain
- inefficient logistics between generators and recyclers
- absence of incentives for households and businesses
- CSR spending lacks measurable, verified reporting
- recyclers struggle with consistent supply chain

As a result, recyclable waste ends up in landfills, causing environmental damage and lost economic value.

---

## 3. Goals & Objectives

### Primary Goals
- Enable structured waste pickup and segregation workflows.
- Provide AI-based waste classification and recyclability scoring.
- Optimize pickup scheduling and collector routing.
- Connect waste supply (generators) with recycling demand (processors).
- Provide transparent impact metrics for CSR and municipal reporting.

### Secondary Goals
- Provide reward points and gamification for segregation behavior.
- Provide dashboards for performance tracking and analytics.
- Build a scalable Bharat-ready platform for circular economy expansion.

---

## 4. Stakeholders & User Roles

### 4.1 Waste Generator
Examples:
- households
- apartments
- hotels
- restaurants
- offices
- industries

### 4.2 Collection Partner / Collector
Examples:
- municipal workers
- private waste pickup teams
- logistics providers

### 4.3 Recycler / Processing Unit
Examples:
- plastic brick and tile manufacturers
- composting units
- pelletizers
- scrap processors

### 4.4 CSR Sponsor / NGO
Examples:
- CSR-funded sustainability programs
- NGOs verifying recycling activity

### 4.5 Municipality / Admin
Examples:
- municipal waste management bodies
- pollution monitoring agencies

---

## 5. Functional Requirements

## 5.1 User Registration & Authentication
- Users should be able to register under roles:
  - Generator
  - Collector
  - Recycler
  - CSR Sponsor
  - Admin
- Login should support OTP/password.
- Role-based dashboards should be provided.

---

## 5.2 Waste Listing & Pickup Request
- Waste generators should create pickup requests with:
  - waste category (plastic, food, paper, metal, e-waste)
  - estimated quantity/weight
  - pickup location
  - preferred time slot
  - optional photo upload

---

## 5.3 AI Waste Classification
- System should allow waste photo upload.
- AI should predict:
  - waste type (PET, HDPE, mixed plastic, organic, paper, etc.)
  - recyclability score (0–100)
- AI should suggest segregation instructions in simple language.

Example:
"This is PET plastic. Please wash and dry before pickup."

---

## 5.4 Smart Pickup Scheduling
- System should assign pickups based on:
  - distance
  - collector availability
  - vehicle capacity
  - waste type compatibility
- System should generate optimized pickup routes.

---

## 5.5 Waste Traceability (QR + Batch Tracking)
- Each pickup must generate a unique batch ID.
- Batch should be tracked across:
  - pickup
  - transport
  - recycler processing
  - final product output
- QR code should be generated for waste batch and output products.

---

## 5.6 Recycler Marketplace Matching
- Recyclers should view waste batch listings.
- Each listing should include:
  - waste type
  - quantity
  - location
  - quality score
  - recyclability score
- Recyclers can accept or bid for batches.

---

## 5.7 Waste-to-Product Output Tracking
- Recycler should update:
  - input waste weight
  - processing method (extrusion/molding/composting)
  - output product type and quantity
  - residue percentage
- System should calculate:
  - conversion ratio
  - efficiency score
  - CO₂ savings estimate

---

## 5.8 CSR Sponsorship & Verified Reporting
- CSR sponsors can fund:
  - waste pickup drives
  - recycling plant operations
  - school/college waste programs
- Sponsor should receive impact report:
  - tons recycled
  - landfill avoided
  - CO₂ saved
  - product output created
  - beneficiaries impacted

---

## 5.9 Rewards & Gamification System
- Generators earn points based on:
  - segregation quality
  - frequency
  - quantity
- Points can be redeemed as:
  - vouchers/cashback
  - discount coupons
  - community recognition badges

---

## 5.10 Dashboards & Analytics
### Generator Dashboard
- pickup history
- rewards earned
- segregation score

### Collector Dashboard
- assigned pickups
- optimized route view
- completed pickups

### Recycler Dashboard
- waste batch availability
- processing history
- output summary

### CSR Dashboard
- funded projects
- verified impact reports

### Admin Dashboard
- city/region recycling performance
- collector and recycler monitoring
- CSR campaign insights

---

## 5.11 Multi-Language Support
- System should support:
  - English
  - Hindi
  - Kannada (Phase-2)

---

## 6. Non-Functional Requirements

### Performance
- Pickup request creation should take < 3 seconds.
- Dashboards should load within 5 seconds.

### Scalability
- Support multi-city deployment.
- Support large campaigns and concurrent requests.

### Security
- Role-based access control.
- Secure OTP login.
- Encrypted storage of sensitive data.

### Reliability
- Pickup history and batch logs must be auditable and consistent.

### Usability
- Minimal clicks, Bharat-friendly UI.
- Simple flow for low-tech users.

---

## 7. Assumptions
- Users have basic smartphone access.
- Collectors and recyclers are verified.
- CSR sponsors demand transparent proof of recycling.

---

## 8. Constraints
- AI accuracy depends on image quality.
- Route optimization depends on map APIs.
- Some processing updates require manual verification.

---

## 9. Success Metrics
- Increase segregation at source.
- Reduction in landfill dumping.
- Improved recycler supply chain consistency.
- Verified CSR impact reporting adoption.
- Increased output of recycled construction products.

---

## 10. Future Enhancements
- IoT smart bins for auto measurement.
- Blockchain-based tamper-proof recycling proof.
- Carbon credit marketplace integration.
- AI forecasting for waste generation patterns.
- Municipality API integrations.
