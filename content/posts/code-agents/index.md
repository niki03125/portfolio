---
title: "Code Agents"
date: 2026-04-20
description: "xxx"
image: "chatbot-cover.jpg"
github: "PASTE-YOUR-GITHUB-LINK-HERE"
draft: false
---

## Project Overview

// lav om 
This project is a **RAG chatbot** built as part of my AI-driven application development course.  
The goal was to create a chatbot that can answer questions based on a specific set of documents instead of only relying on the model's general knowledge.

RAG stands for **Retrieval Augmented Generation**.  
This means the chatbot first searches through selected material, retrieves the most relevant information, and then uses that information to generate an answer.

## What the Chatbot Does

// lav om 
The chatbot allows a user to ask questions about a chosen set of documents or course material.

Instead of answering freely from the language model alone, it:
1. receives a question from the user  
2. searches relevant text chunks in the uploaded material  
3. retrieves the most relevant information  
4. uses that context to generate a grounded answer  

This makes the chatbot more useful when working with specific documents, notes, or learning material.

## How I Built It
// lav om 
To build this project, I worked with the basic RAG pipeline:

- I started with a set of documents or text material
- The material was split into smaller chunks
- These chunks were converted into embeddings
- The embeddings were stored so they could be searched
- When the user asks a question, the system retrieves the most relevant chunks
- The retrieved text is then sent together with the prompt to the language model
- The model generates an answer based on that context

The main idea was to connect **my own material** to an LLM in a structured way.

## Why RAG is Useful
// lav om 
One of the important things I learned is that RAG can be very useful when you want answers based on specific sources.

RAG is valuable because it can:
- make answers more relevant to a chosen topic
- reduce hallucinations
- let the chatbot use custom documents
- make it easier to build domain-specific assistants

At the same time, RAG also has limitations:
- the answer quality depends on the quality of the source material
- chunking and retrieval strategy matter a lot
- if the wrong context is retrieved, the answer can still be weak
- it is not always the best solution for every task

## What I Learned
// lav om 
Through this project, I learned more about:

- how RAG architecture works in practice
- how embeddings are used to represent text
- how retrieval helps connect a language model to external knowledge
- the difference between a normal chatbot and a RAG-based chatbot
- why data quality and structure are important in AI systems

I also learned that building AI applications is not only about the model itself, but also about the pipeline around it.

## Technologies Used
// lav om 
- Large Language Model (LLM)
- Retrieval Augmented Generation (RAG)
- Embeddings
- Document chunking
- Retrieval / semantic search

## Reflection
// lav om 
This project gave me a practical introduction to how modern AI assistants can be connected to real data.

It was especially interesting to see how a chatbot becomes more useful when it can answer from selected material instead of only general model knowledge.  
This made the project feel more realistic and closer to real-world AI applications.

## GitHub Repository

[View the project on GitHub](PASTE-YOUR-GITHUB-LINK-HERE)

## Screenshots

Add screenshots of the chatbot here.

![Chatbot screenshot](chatbot-screenshot.jpg)