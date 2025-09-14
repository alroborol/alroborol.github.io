---
title: "Why You Should Build AI Agents with Ollama First"
meta_title: "Build AI Agents with Ollama first to understand the architecture risks in the early stage"
description: "Distinguishing between AI model limitations and engineering limitations can be hard for AI services. Build AI Agents with Ollama first to understand the architecture risks in the early stage."
date: 2025-10-10T22:08:00Z
image: "/images/blog-3.png"
categories: ["Technology", "Insight"]
author: "Al Roborol"
tags: ["Technology", "Agent", "LLM"]
draft: false
---
## The AI PoC Paradox: High Effort, Low ROI

Building AI Proofs of Concept (PoCs) has become routine in many DX departments. With the rapid evolution of LLM models, more and more AI agents with new capabilities come every day. But Return on Investment (ROI) doesn’t change in the same way. Why is that?

One reason might be that while LLM capabilities are advancing at breakneck speed, our AI engineering techniques for bridging these powerful models with real-world problems are lagging. We get excited about new features and use cases enabled by the latest models, but real-world returns remains unimproved due to a lack of robust engineering practices.

## Simulating Real-World Constraints with Ollama

So, how can we estimate the real-world accuracy of our AI PoCs? One easy approach is to start building your AI agents with Ollama. Ollama allows you to run a selection of LLM models locally with limited resource requirements. By beginning with Ollama, you face the challenges of difficult input from users in the early stage. Those challenges may remain hidden when a powerful LLM is used.

The limitation made visible are context window size (input being too long) and scalability (ignored small overheads become innegligible):

### Realistic Context Handling

- **Realistic Context Handling:** Ollama's local execution has a default 4K context window size. Unlike cloud-based models with infinite contexts that can hide over-size retrieved context, Ollama exposes the out-of-size issue early. This helps developers understand what are the possible pitfalls in Retrieval Augmented Generation (RAG), ensures that an AI agent delivers good results even when some accidents happens. 

### Confronting Improper Workflow

- **Confronting Improper Workflow:** The inference speeds on Ollama, around 20 tokens/second for a 4B model on a powerful CPU-only PC. Generating a summary take tens of seconds, which is just right. You won’t feel slow if LLM workflow is as you expected. And you will immediately feel strange if the agent gets into unnecessary loops or side tasks. Cloud services like ChatGPT and Claude infer so rapidly that bad workflow loops may only feel like a 10-second pause. Average PCs expose slow parts in apps. And average LLMs expose slow workflows.

## Navigating Production Transition and Migration

Even if you're persuaded by the benefits, you might worry about the cost of migrating an Ollama AI service to OpenAI LLMs and  cloud platforms like AWS. You can start with local AWS to reduce costs. Standard cloud components like S3 and Lambda have readily available local alternatives, such as those provided by LocalStack. 

However, if your architecture relies on specific cloud provider tweaks or runs on platforms like Azure, the migration might require more effort. Ollama may not be a good option for you.

Nevertheless, even without using Ollama, limiting your model choice to under 14B parameters can be beneficial for accurately assessing PoC efficacy early on.

Have fun experimenting with your AI PoCs!
