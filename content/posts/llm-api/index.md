---
title: "Fullstack Setup & Debugging (Spring Boot + Vite)"
date: 2026-04-27
description: "Setting up a fullstack application with a Java Spring Boot backend and a Vite frontend, including debugging real-world issues like BOM errors, environment setup, and port conflicts."
featureimage: "/chatbot-cover.jpg"
showHero: true
heroStyle: "basic"
github: "https://github.com/niki03125/portfolio"
draft: false
---

## Project Overview

In this project, I worked on setting up a **fullstack application** consisting of a Java backend and a modern frontend.

The goal was to run both parts locally and connect them, but the process turned into a deep dive into **debugging and understanding how development environments actually work**.

Instead of just writing code, I spent a lot of time solving issues related to setup, configuration, and system behavior — which ended up being one of the most valuable learning experiences.

---

## Running Backend and Frontend Together

The application is split into two main parts:

- A **Spring Boot backend** running on:
  http://localhost:8080

- A **Vite frontend** running on:
  http://localhost:5173

To make everything work, both systems must run at the same time.  
The frontend communicates with the backend using API requests.

This setup reflects how many real-world applications are structured.

---

## Debugging Process and Errors

While setting up the project, I encountered several different types of errors.  
Instead of just fixing them quickly, I focused on understanding **why they happened**, which helped me gain a much deeper understanding of the system.

---

### Environment Setup Issues

At the beginning, I ran into problems simply trying to start the backend.

The first issue was that Maven was not recognized:

mvn : not recognized

This happened because Maven was not installed or configured correctly in my system PATH.  
After installing Maven and setting up the environment variables, I was able to run backend commands.

---

### Java Version Conflict

After getting Maven working, I encountered another issue:

class file has wrong version 61.0, should be 55.0

This error means that the project was built using a newer Java version than the one currently running.

- Version 61 = Java 17  
- Version 55 = Java 11  

Spring Boot 3 requires Java 17, but my system was using Java 11.

I solved this by running the backend inside IntelliJ using Java 17, which made everything compatible.

---

### BOM (Byte Order Mark) Error

One of the more confusing errors I encountered was:

illegal character: '\ufeff'

This turned out to be caused by something called a **BOM (Byte Order Mark)**.

A BOM is an invisible character placed at the beginning of a file to indicate encoding.  
While it can be useful in some contexts, it breaks many development tools.

For example, a file might look like this:

﻿{
  "name": "project"
}

That hidden character before `{` is enough to break Java and JSON parsing.

The issue happened because some tools saved files as:

UTF-8 with BOM

I fixed this by changing the encoding to:

UTF-8 (without BOM)

and saving the files again.

---

### Frontend Setup Issues

When setting up the frontend, I encountered errors related to Node and Vite.

At first, Vite was not recognized:

'vite' is not recognized

This was because the dependencies had not been installed.  
Running:

npm install

fixed the issue.

---

Another issue occurred when trying to start the frontend:

Could not read package.json

This happened because I ran the command in the wrong directory.

The fix was simply:

cd frontend  
npm run dev

---

### Port Conflicts

When running the backend, I also encountered this error:

Port 8080 was already in use

This meant that another process was already using the port.

I identified and stopped the process using:

netstat -ano | findstr :8080  
taskkill /PID <id> /F  

After that, the backend started successfully.

---

## What I Learned

This project taught me that building applications is not just about writing code — it is also about understanding the environment in which the code runs.

I learned:

- how frontend and backend systems interact  
- how environment variables and system configuration affect applications  
- how encoding (like BOM) can break code in unexpected ways  
- how to debug real-world errors step by step  
- how to read and understand error messages instead of ignoring them  

---

## Reflection

This project was a great example of how development often involves solving problems that are not directly related to the application logic.

Many of the issues I encountered were:

- configuration problems  
- system-level errors  
- hidden bugs (like BOM)  

By working through these challenges, I gained a much better understanding of how fullstack systems operate in practice.

Instead of just building features, I learned how to **debug, analyze, and fix complex issues**, which is an essential skill in software development.

---

## GitHub Repository

[View the project on GitHub](https://github.com/niki03125/AI-vurdering-af-en-opgave-ud-fra-en-rubric)