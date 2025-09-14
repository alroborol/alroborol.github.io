---
title: "MCP: Standardizing How AI Interacts with the World—But Capability Negotiation Remains Unsolved"
meta_title: "MCP: Standardizing How AI Interacts with the World—But Capability Negotiation Remains Unsolved"
description: "Even though MCP aims to be like a USB-C protocol, differences in knowledge and context windows between LLMs are fundamental barriers. Simply standardizing the exchange of function lists is not enough."
summary: "Even though MCP aims to be like a USB-C protocol, differences in knowledge and context windows between LLMs are fundamental barriers. Simply standardizing the exchange of function lists is not enough."
date: 2025-09-14T15:42:00Z
image: "/images/image-placeholder.png"
categories: ["Technology", "Insight"]
author: "Al Roborol"
tags: ["Technology", "MCP", "LLM"]
draft: false
---


**MCP (Machine Context Provisioning)** has become a buzzword in the age of AI. Its developer, Anthropic, describes MCP as a “USB-C port for AI applications.” The goal of MCP is to standardize how applications provide context to large language models (LLMs).

But what does it mean to *provide context to an LLM*? And what exactly is *context*?

For example, when booking a flight ticket, your schedule and preferences become the context. Intuitively, you might think of related information as context—and that’s correct.

However, MCP’s promotion tends to oversimplify the possibilities of user scenarios.

## Before MCP: Function Calls Were Already Powerful

Even before MCP, LLMs could obtain context and execute system commands through function calls. AI agents could fix build errors using the Linux shell or perform web searches.

However, function calls depended on specific LLM models or SDKs (e.g., LangChain), making it difficult to share between different LLMs or tools.

## MCP Is More Than Just Context

MCP is not just a tool for providing context. MCP is the “hand” that allows LLMs to interact with the world.

Anything you can do with function calls, you can also do with MCP.

- Automated testing using Android’s ADB? No problem: [Android MCP Server](https://mcpservers.org/servers/minhalvp/android-mcp-server)
- Controlling UART devices with AI? Try this: [UART MCP Server](https://github.com/alroborol/mcp-uart)

For example, even without knowledge of Android, I was able to retrieve the device’s battery status.

## Missing Capability Check: The Big Issue for MCP

MCP aims to solve this problem by wrapping available function calls in a generic JSON list, making them easily accessible through a standardized API.

However, due to the lack of capability negotiation, true interoperability remains a challenge.  
You can try this out with Zed and ollama. Choose mistral and enable MCP tools like Context7, and ask Zed to do something with the tool. You will find Zed not calling the tool.

Even though MCP aims to be like a USB-C protocol, differences in knowledge and context windows between LLMs are fundamental barriers. Not to mention when you have 100+ MCP tools enabled. Simply standardizing the exchange of function lists is not enough.

MCP can be universal among the latest cloud models, but not with legacy or small models. This can be a big issue for enterprise MCP usage.

## The Next Step: Compatible and Efficient Tool Calling

To make MCP work reliably and efficiently, well-planned tool calling is necessary. When multiple MCP tools are available, LLMs may struggle to choose the most appropriate one, especially if tools have overlapping capabilities or require complex arguments.

One approach is to implement an MCP tool router—a middleware layer that analyzes the user's intent and context, then selects the best tool for the task. This router can use metadata about each tool, such as supported operations, required arguments, and compatibility with different LLMs, to make informed decisions.

Additionally, a tool calling helper can guide LLMs in constructing valid function calls. This helper can prompt the LLM for missing arguments, validate input formats, and even suggest alternative tools if the initial call fails. By combining a router and a helper, the system can reduce errors, improve interoperability, and streamline the user experience.

Experimentation is ongoing, but these enhancements could make MCP tool calling more robust, scalable, and user-friendly—especially in environments with dozens or hundreds of available tools.

## In Conclusion

MCP is more than just a context provider—it’s an interface for LLMs to connect with the outside world. Anything possible with function calls is also possible with MCP. You might find even more creative uses.

**Enjoy MCP!**