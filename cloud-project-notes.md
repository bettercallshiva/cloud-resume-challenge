# Cloud Resume Challenge
# Cloud Resume Challenge - Project Notes

## Project Goal

Build a cloud-focused portfolio website and gradually deploy it using cloud technologies. The project will demonstrate skills in:

* Git
* GitHub
* React
* Deployment
* AWS (future phase)
* Cloud & DevOps fundamentals

---

## Phase 1: Local Development Setup

### Objectives

* Install Node.js
* Verify npm
* Create a React application using Vite
* Run the application locally

### Commands Used

Check Node.js:

node -v

Check npm:

npm -v

---

### PowerShell Issue

Error:

npm.ps1 cannot be loaded because running scripts is disabled on this system

Fix:

Set-ExecutionPolicy -Scope CurrentUser RemoteSigned

Result:

npm started working successfully.

---

## Phase 2: React Project Creation

### Create Project

npx create-vite@latest cloud-resume-challenge --template react

### Navigate into Project

cd cloud-resume-challenge

### Install Dependencies

npm install

### Run Development Server

npm run dev

Output:

Local: http://localhost:5173

Result:

React application successfully running locally.

---

## Phase 3: Project Customization

Updated App.jsx to create a personal portfolio page.

Current content includes:

* Name
* Cloud & DevOps Enthusiast title
* Learning goals
* Project list
* GitHub profile

Purpose:

Transform default Vite template into a professional portfolio.

---

## Phase 4: Git & GitHub

### Create Git Repository

git init

### Add Files

git add .

### Create Initial Commit

git commit -m "Initial cloud resume project"

---

## GitHub Repository

Repository Name:

cloud-resume-challenge

Repository URL:

https://github.com/bettercallshiva/cloud-resume-challenge

---

## Connect Local Repository

git remote add origin https://github.com/bettercallshiva/cloud-resume-challenge.git

git branch -M main

---

## Push Code

git push -u origin main

---

## Issues Encountered

### Authentication Error

Error:

Invalid username or token

Cause:

GitHub no longer supports password authentication.

Resolution:

Configured Git authentication and signed into GitHub.

---

### Merge Conflict

Error:

README.md conflict

Cause:

Both local repository and GitHub repository contained README files.

Resolution:

Resolved conflict manually and committed changes.

Command:

git add README.md

git commit -m "Resolve README merge conflict"

git push -u origin main

Result:

Code successfully pushed to GitHub.

---

## Current Project Status

Completed:

✅ Node.js Setup

✅ npm Setup

✅ React Project

✅ Local Development

✅ Git Initialization

✅ GitHub Repository

✅ First Commit

✅ Push to GitHub

✅ Merge Conflict Resolution

---

## Future Roadmap

### Phase 5

Deploy to GitHub Pages

Technology:

React → GitHub → GitHub Pages

Outcome:

Public website URL

---

### Phase 6

AWS Deployment

Technology:

React → S3 → CloudFront

Outcome:

Cloud-hosted portfolio website

---

### Phase 7

Visitor Counter

Technology:

API Gateway → Lambda → DynamoDB

Outcome:

Serverless cloud architecture

---

### Phase 8

Infrastructure as Code

Technology:

Terraform

Outcome:

Automated AWS infrastructure provisioning

---

## Skills Learned So Far

* PowerShell troubleshooting
* Node.js setup
* npm package management
* React fundamentals
* Vite project creation
* Git basics
* GitHub workflow
* Commit management
* Merge conflict resolution
* Repository management

---

## Resume Impact

Project:

Cloud Resume Challengegit sta

Skills Demonstrated:

React, Git, GitHub, Deployment Workflows, Cloud Fundamentals

Repository:

https://github.com/bettercallshiva/cloud-resume-challenge
---

## Linux Environment Setup (WSL)

### Objective

Move development workflow from Windows PowerShell to Ubuntu Linux (WSL2).

### Commands Learned

whoami
pwd
ls
cd
git --version
node -v
npm -v

### Results

- Ubuntu 24.04 LTS verified
- WSL2 functioning correctly
- Node.js installed inside Ubuntu
- npm installed inside Ubuntu
- React application runs successfully from Linux terminal
- Project accessible via /mnt/c/Users/HP/Desktop/cloud-resume-challenge

### Key Learning

Most cloud environments use Linux. Working from Ubuntu provides experience closer to real cloud servers and DevOps environments.

### Skills Gained

- Linux terminal navigation
- WSL usage
- Linux package management
- Cross-platform development workflow