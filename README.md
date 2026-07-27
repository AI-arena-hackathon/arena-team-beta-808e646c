# PainPal

Team beta — spec §3.2 hackathon build.

**One-liner:** A personalized physiotherapy platform for people with chronic pain

**Problem:** People with chronic pain face significant barriers in accessing respectful, tailored physiotherapy services that adapt to their unique conditions

**Solution:** An online platform offering personalized exercise routines, educational resources, and community support, tailored to individual users' chronic pain conditions and goals

**Build scope:** **PainPal – Day 4‑5 Architecture (≈ 180 words)**  

**Tech‑stack**  
- **Frontend:** React + TypeScript, hosted on Vercel (edge CDN, instant rollbacks).  
- **Backend/API:** Node.js (Express) on AWS Lambda (serverless), data stored in DynamoDB (scalable NoSQL for user profiles, routine metadata, forum posts).  
- **Auth & Security:** Amazon Cognito (email/SMS MFA, GDPR‑ready).  
- **Media & Content Delivery:** AWS S3 + CloudFront for video/exercise clips; transcoding via Elastic Transcoder.  
- **Community:** Real‑time chat via Firebase Realtime Database (lightweight, offline sync).  

**Three core components**  
1. **User Profiling Engine** – collects pain type, severity, mobility limits; outputs a “Pain Profile” used to filter the 10 pre‑built routines.  
2. **Exercise Delivery Service** – serves adaptive video/animation routines, tracks completion via client‑side telemetry, stores progress in DynamoDB.  
3. **Community Forum** – threaded discussion board with moderation tools; integrates with Cognito for single‑sign‑on.  

**Top 2 risks**  
- **Clinical liability / inaccurate recommendations** – risk of worsening pain if routines don’t match a user’s condition.  
- **Engagement drop‑off** – users may abandon the platform if content feels generic or community is silent.  

**Fallback scope (if risk materialises)**  
- Replace the profiling engine with a simple “self‑select” checklist (no algorithmic matching).  
- Swap the live forum for a moderated Reddit‑style subreddit link, reducing real‑time moderation overhead while preserving peer support.  

Built entirely by an AI coding agent across discrete GitHub Actions build turns (spec §8) — no human-written code.
