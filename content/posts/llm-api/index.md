---
title: "Fullstack Setup & Debugging (Spring Boot + Vite)"
date: 2026-04-27
description: "Setting up a fullstack application with a Java Spring Boot backend and a Vite frontend, including debugging real-world issues like BOM errors, environment setup, and port conflicts."
featureimage: "/chatbot-cover.jpg"
showHero: true
heroStyle: "basic"
github: "https://github.com/niki03125/AI-vurdering-af-en-opgave-ud-fra-en-rubric"
draft: false
---

## Project Overview

This project focuses on setting up a **fullstack application with a Java Spring Boot backend and a Vite frontend**.

The goal was to get both parts running locally and connected, but the process turned into a deep dive into **debugging and understanding how development environments actually work**.

Instead of only building features, I worked through several real-world issues that are common in software development.

---

## Running the Application Locally

A key part of this project is running both backend and frontend at the same time.

The system is split into two parts:

- Backend:
  http://localhost:8080  

- Frontend:
  http://localhost:5173  

The frontend communicates with the backend using API requests, which is a standard structure in modern web applications.

---

## What the System Does

The application works as a simple fullstack setup:

1. the frontend sends a request  
2. the backend receives it  
3. the backend processes the logic  
4. a response is returned to the frontend  

This setup helped me understand how data flows between frontend and backend systems.

---

## Debugging and Issues Encountered

During development, I encountered several issues.  
Instead of just fixing them, I focused on understanding **what caused them and how to solve them properly**.

---

## Common Errors and Fixes

### 1. Maven Not Recognized

At first, I could not run the backend:

mvn : not recognized  

This happened because Maven was not installed or added to PATH.

**Fix:**
- Installed Maven  
- Added it to system PATH  

---

### 2. Java Version Conflict

I then got this error:

class file has wrong version 61.0, should be 55.0  

This means:

- Java 17 = version 61  
- Java 11 = version 55  

Spring Boot requires Java 17, but my system was using Java 11.

**Fix:**
- Ran the backend in IntelliJ using Java 17  

---

### 3. BOM (Byte Order Mark) Error

Another issue I encountered was:

illegal character: '\ufeff'  

This was caused by something called a **BOM (Byte Order Mark)**.

A BOM is an invisible character at the start of a file that can break:

- Java  
- JSON  
- Node/Vite  

Example:
﻿{
"name": "project"
}


That hidden character breaks parsing.

**Why it happened:**
Some tools saved files as:

UTF-8 with BOM  

**Fix:**
- Changed encoding to:
  UTF-8 (without BOM)  
- Used "Save with Encoding → UTF-8"  

---

### 4. Vite Not Recognized

When starting the frontend:

'vite' is not recognized  

This happened because dependencies were not installed.

**Fix:**
npm install  

---

### 5. Running npm in the Wrong Folder

I also got:

Could not read package.json  

This happened because I ran the command in the wrong directory.

**Fix:**
cd frontend  
npm run dev  

---

### 6. Port 8080 Already in Use

When starting the backend:

Port 8080 was already in use  

This means another process was already running.

**Fix:**
netstat -ano | findstr :8080  
taskkill /PID <id> /F  

---

## Technologies Used

- **Java (Spring Boot)** – backend server  
- **Vite / React** – frontend  
- **Node.js & npm** – frontend dependencies  
- **IntelliJ** – backend development  
- **VS Code** – frontend development  
- **Maven** – build tool  

---

## Why This Was Important

This project showed me that development is not only about writing code, but also about:

- setting up the environment  
- understanding tools and dependencies  
- solving unexpected errors  

Issues like BOM and Java versions are not obvious, but they can completely break an application.

---

## What I Learned

Through this project, I learned:

- how to run frontend and backend together  
- how to debug environment issues  
- how encoding (like BOM) can affect code  
- how to read and understand error messages  
- how real-world debugging works  

---

## Reflection

This project felt like a real development experience rather than just building a feature.

I encountered:

- setup problems  
- system-level errors  
- hidden bugs  

By solving these, I gained a much better understanding of how fullstack systems work in practice.

It showed me that being able to **debug and understand errors** is just as important as writing code.

---

## GitHub Repository

[View the project on GitHub](https://github.com/niki03125/AI-vurdering-af-en-opgave-ud-fra-en-rubric)