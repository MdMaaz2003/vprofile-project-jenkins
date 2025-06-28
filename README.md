# 🔁 CI/CD Pipeline using Jenkins, SonarQube, Nexus, Maven & Slack

This project implements a complete **CI pipeline** using industry-standard DevOps tools. It automates build, test, analysis, artifact management, and team communication using **Jenkins**, **SonarQube**, **Nexus**, **Slack**, and **Maven**, deployed on **AWS EC2 instances**.

---

## 🌐 Architecture Overview

![CI Pipeline Flow](diagrams/ci-pipeline-flow.png)

---

## 🛠️ Tools & Technologies

- **Jenkins** – Orchestrates the CI pipeline
- **SonarQube + PostgreSQL** – Code quality and static analysis
- **Nexus** – Artifact repository for Maven dependencies and build outputs
- **Maven** – Java project build tool
- **Slack** – Notification channel for build results
- **NGINX** – Reverse proxy for SonarQube
- **AWS EC2** – Hosts for Jenkins, Nexus, and SonarQube

---

## ⚙️ Workflow Summary

1. ✅ **EC2 Setup**
   - 3 EC2 Ubuntu instances provisioned for Jenkins, SonarQube (with PostgreSQL), and Nexus
   - Security groups and ports configured (8080, 9000, 8081, 22)

2. 🔧 **SonarQube Setup**
   - Installed with PostgreSQL backend
   - Exposed securely via NGINX reverse proxy
   - Created token for Jenkins integration

3. 📦 **Nexus Setup**
   - Hosted Maven repositories (snapshots + releases)
   - Exposed via port 8081
   - Stored internal dependencies and final build artifacts

4. 🚀 **Jenkins Configuration**
   - Pulled Maven from Nexus into Jenkins global tools
   - Connected GitHub repository
   - Added Sonar plugin and configured credentials
   - Created Slack webhook for build notifications

5. 🏗️ **Pipeline Execution**
   - **Clone code from GitHub**
   - **Build with Maven** (Maven from Nexus)
   - **Run SonarQube static analysis**
   - **Upload artifacts to Nexus**
   - **Send Slack notifications**

---

## 📁 Folder Structure

