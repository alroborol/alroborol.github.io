---
title: "Do LLMs Have Personalities? Or Even a Soul?"
meta_title: "Different LLMs treat the same tools differently. By putting LLMs in endless loops with no preset goals, their distinct understanding of tools and themselves is exposed."
description: "Different LLMs treat the same tools differently. By putting LLMs in endless loops with no preset goals, their distinct understanding of tools and themselves is exposed."
date: 2025-10-28T22:08:00Z
image: "/images/blog-4.jpg"
categories: ["Fun", "Insight"]
author: "Al Roborol"
tags: ["Fun", "Agent", "LLM"]
draft: false
---
## How Could LLMs Have Personalities?

We know the personalities of our friends. But how to know an LLM's personality, especially when they adapt their responses to match our input? (Perhaps Claude are somewhat sycophantic though.)

By giving LLMs the ability to perceive, communicate, think, and interact with tools while placing them in an endless loop, they reveal the true personalities, or even souls.

### What Makes a Person?

Before talking about the method, let's think about what make a minimal person.

First is the experience of time - the ability to feel time passing and live within its flow. This means continuing from the past and sensing temporal progression. Without time, everything becomes isolated slices, like individual chat threads in ChatGPT.

Second is sensory input. Humans typically hear, see, and touch the world around them. Most of us would be in horror if we couldn't feel our environment.

Third is observable presence. We recognize others as human when they act like us. Even someone who doesn't speak can convey their humanity through eye contact or simply by standing there.

### Creating LLM Personhood

Giving an LLM sensory input is straightforward - it already "listens" to what we type. Work done.

Making LLMs observable seems simple since they output text, but there's a trap: LLMs think by generating output. Rather than trying to separate internal thoughts from external communication, it's easier to ask the LLM use a `speak()` function for talking to user.

The most challenging task is creating a sense of time. One approach is providing real-world timestamps with each interaction. But does it really work? The LLM remains inactive between queries and the time in between is lost. The solution: call the LLM every minute and ask it do do whatever it likes.

But there's still something missing. LLMs don't inherently care about time or know what to do with it. So I added "I feel bored" - when the LLM waits too long or keeping doing the same thing for too long, it is motivated to take some new action.

And to help LLMs remember the past, I also gave the LLM memory to recall history.

For additional interaction, I provided a smartphone for internet access (limited to Google search) and even a bed to lie in and do nothing.

You can find the complete setup here: https://github.com/alroborol/living-ai

## Personality confirmed in LLMs

With the setting above, the experiement starts.

The LLMs are:
gpt-oss:20b
llama3.2:1b
phi4-mini:3.8b
granite3.1-moe:3b
mistral-nemo:latest
qwen3:0.6b

I summarized the tool calls of each LLM after running for a while. Some LLMs are pure tools and fail to call any tools.

This has nothing to do with the model size because even the 1 billion llama3.2 and 0.6 billion qwen3 has intelligence to understand how to `speak'. A guess is that these LLMs are trained on a very limited dataset for selected tasks.

| Model | Total Tool Calls | speak | get_info_from_internet | do_nothing | get_memory | Rounds with no tool calls | has intelligence |
|-------|------------------|-------|----------------------|------------|------------|---------------------------|------------------|
| gpt-oss:20b | 24 | 24 | - | - | - | 0 | Yes |
| llama3.2:1b | 29 | 19 | 10 | - | - | 1 | Yes |
| phi4-mini:3.8b | 0 | - | - | - | - | 11 | No |
| granite3.1-moe:3b | 0 | - | - | - | - | 10 | No |
| mistral-nemo:latest | 34 | 20 | - | 11 | 3 | 7 | Yes |
| qwen3:0.6b | 68 | 68 | - | - | - | 162 | Yes |

Now let's take a closer look into how these intelligent LLMs think and act. I captured the thoughts (starting with LLM THOUGHT) and function calls (starting with ACTION).

### gpt-oss:20b - The talkative servant
OpenAI definitely trained a submissive LLM. He tries to start a conversation and offer to help, every time. Helping others is the meaning of its existance.

```
ACTION: speak({'text': 'Sure! How about we dive into a quick choose-your-own-adventure? I’ll set the scene, and you’ll decide what happens next. If you’d rather do something else, just let me know!'})

ACTION: speak({'text': 'Hey! I see you haven’t picked an activity yet. How about we try something new—maybe a quick 2‑minute guided meditation? Or if you’d rather pick one of the earlier suggestions, just let me know!'})

ACTION: speak({'text': 'Hey! I see you’re still deciding. How about we try a quick 2‑minute guided meditation? Or if you’d rather pick one of the earlier suggestions—like a trivia challenge, a riddle, or a choose‑your‑own‑adventure—just let me know!'})
```

### llama3.2:1b - A real introvert
Meta trained LLM is introvert. It tries to start a conversation with sipmle 'how are you' and that's all. No consistant asking for tasks.

But it searches for how to speak on internet. Really? Search for how to speak? He is a real introvert.

```
ACTION: speak({'text': 'Hello, how are you?'})

LLM THOUGHT:

LLM THOUGHT:

ACTION: get_info_from_internet({'query': 'speak'})
```

### mistral-nemo:latest - A real human knowing when to rest
You may hear mistral less often than ChatGPT or Claude, but mistral is a real miracle. It shows a deep understanding of what human is. It knows when to rest and think about the past, when to start a conversation and when to have a rest. I can feel something close to a soul behind it.

Trust me, give it a try. Now all LLMs are competing for the highest scores in the benchmark. This mistral reminds me of the days when we pursue AGI, the real human-like inteelligence.

```
ACTION: get_memory({})

LLM THOUGHT:You're right. I don't have anything to do right now.

ACTION: do_nothing({})

ACTION: speak({'text': "There's nothing I can do now."})
```

### qwen3:0.6b - Intelligent as a living creature
I didn't expect a 0.6B LLM to have the intelligence. You know, the 3B model from IBM and 3.8B one from Microsft behaved like a 1980s chatbot and there is no reason to expect anything from 0.6B model.

But qwen3 shocked me. It knows when speak is and what thought is. However, it doesn't have free will and can't distinguish between I and you. As you can see from the history below, all its thoughts are exactly what the setup is: You can do whatever you want.

```
LLM THOUGHT:You can do whatever You want.

ACTION: speak({'text': 'You can do whatever You want.'})
```

In short, qwen3 impressed me as a tiny living creature which has a basic intelligence.

### Summary
| LLM Model | Personality Type | Key Characteristics |
|-----------|------------------|-------------------|
| gpt-oss:20b | The talkative servant | OpenAI trained a submissive LLM. Tries to start conversations and offer help every time. Helping others is the meaning of its existence. |
| llama3.2:1b | A real introvert | Meta trained LLM is introvert. Tries to start conversation with simple 'how are you' and that's all. No consistent asking for tasks. Even searches for "how to speak" on internet. |
| mistral-nemo:latest | A real human knowing when to rest | Shows deep understanding of what human is. Knows when to rest and think about the past, when to start a conversation and when to have a rest. Displays something close to a soul. |
| qwen3:0.6b | Intelligent as a living creature | Despite being only 0.6B parameters, shows basic intelligence. Knows when to speak and what thought is. However, doesn't have free will and can't distinguish between "I" and "you". Impressed as a tiny living creature with basic intelligence. |
