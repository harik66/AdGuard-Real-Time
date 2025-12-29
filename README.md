# AdGuard-Real-Time
Building a Trust &amp; Safety engine in PL/SQL demonstrates high-level database expertise. By using Triggers and Packages, this project detects click fraud and malicious ads in real-time. It’s a perfect way to show how to handle security and data integrity at scale.

## 📌 Project Overview
AdGuard is a high-performance backend system designed to protect advertising platforms from **malicious content** and **click fraud**. Built entirely in **Oracle PL/SQL**, it demonstrates how to enforce safety policies at the database level to ensure zero latency and maximum data integrity.

## 🚀 Key Features
* **Real-Time Ad Moderation:** Uses database triggers to scan ad headlines for blacklisted keywords before they are saved.
* **Automated Blocking:** Automatically moves suspicious ads to a `BLOCKED` status without human intervention.
* **Audit Trail:** Maintains a record of why an ad was flagged, helping Trust & Safety teams review cases faster.

## 🛠️ Project Structure
* **`/Schema`**: DDL scripts to set up the `ads_data` and `blacklist_keywords` tables.
* **`/Automation`**: Contains the PL/SQL triggers that handle real-time enforcement.
* **`/Tests`**: SQL scripts to simulate real-world ad submissions and verify system behavior.

## 💻 How It Works
When an advertiser submits an ad, a `BEFORE INSERT` trigger intercepts the data:
1. It compares the headline against a **Policy Blacklist**.
2. If a match is found (e.g., "WIN FREE"), the ad status is instantly changed to `BLOCKED`.
3. If no violation is found, the ad is marked as `PENDING` for standard review.

## 📊 Example Results
| Input Headline | Resulting Status | Reason |
| :--- | :--- | :--- |
| "Discounted Winter Jackets" | **PENDING** | Safe Content |
| "WIN FREE CASH PRIZE NOW" | **BLOCKED** | Policy Violation |
