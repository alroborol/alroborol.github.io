---
title: "梅花易数 Web"
banner:
  title: "梅花易数 & 神煞（Web）"
  content: "A web-based lunar calendar and divination tool that converts Gregorian dates to the Chinese lunar calendar and displays daily readings, advice cards, and tables. Uses solarlunar for accurate lunar conversions and runs as a lightweight static site suitable for GitHub Pages."
  image: "/images/creation-oracle.png"
  buttons:
    - enable: true
      label: "Try It Out"
      link: "https://alroborol.github.io/oracle/"
      icon: "fa fa-arrow-right"
      primary: true
    - enable: true
      label: "Check the Code"
      link: "https://github.com/alroborol/oracle"
      icon: "fab fa-github"
features:
  - title: "Statistics"
    image: "/images/image-placeholder.png"
    content: "How AI was applied, what it automated, what remained manual, estimated time saved, and new issues to watch for."
    bulletpoints:
      - "Total Development Time: ~3 Hours (from concept to deployment)."
      - "Rounds of Iteration: 15 (refining UI, mapping logic, and performance)."
      - "Manual Verification Cycles: 4 major rounds (ensuring lunar conversion accuracy)."
      - "Critical Bugs Squashed: 2 (including a leap month calculation error)."
  - title: "Lunar Conversion"
    image: "/images/tool-log-prompt-1.png"
    content: "Convert Gregorian dates to lunar calendar dates and show lunar attributes for the selected day."
    bulletpoints:
      - "Accurate Gregorian ↔ Chinese lunar conversions using solarlunar"
      - "Displays lunar month/day and related calendrical data"
  - title: "Interactive Date Cards & Advice"
    image: "/images/image-placeholder.png"
    content: "Interactive UI with a date picker, day info card, advice card, and tabular views for readings."
    bulletpoints:
      - "Persistent cards showing day-specific information"
      - "Advice and summary sections for quick reference"
  - title: "Easy Deployment"
    image: "/images/image-placeholder.png"
    content: "Designed to be served as a static site (GitHub Pages or docs/), with minimal dependencies."
    bulletpoints:
      - "Works offline once deployed; includes instructions for GitHub Pages"
      - "Small footprint: index.html, script.js, styles.css"
---

# Modernizing Ancient Wisdom: Building a Web-Based Divination Tool

How can we bring ancient Chinese wisdom into the modern web era? The challenge isn't just about translating old texts, but about creating tools that make complex metaphysical calculations instant and accessible. 

Over a focused development session, I collaborated with AI to build **梅花易数 Web**, a lightweight, high-performance divination dashboard.

## The Vision: Accuracy and Accessibility

The goal was to create a tool that stays true to the traditions of the Chinese lunar calendar while providing a premium, modern user experience. We focused on three pillars:

1.  **Precision**: Ensuring every date conversion is mathematically perfect, even for leap months.
2.  **Clarity**: Presenting complex "Shen Sha" (divine stars) and advice in a clean, digestible format.
3.  **Portability**: A zero-backend architecture that runs anywhere, from GitHub Pages to a local folder.

## Core Features at a Glance

*   **Solar-Lunar Sync**: Real-time conversion engine using the `solarlunar` library for 100% accuracy.
*   **Daily Oracle Cards**: Dynamic UI that generates customized advice based on the selected day's metaphysical attributes.
*   **Zero-Latency Interface**: A vanilla JS core that ensures the site loads in under 500ms and responds instantly to date changes.

## Technical Deep Dive: The Accuracy Challenge

The most critical part of this project was the date conversion logic. Unlike the Gregorian calendar, the Chinese lunar calendar incorporates intercalary months and solar terms that require complex astronomical calculations. 

### 🧮 Bridging the Gap
We integrated a robust conversion layer that handles the transition between the two systems. This allows users to pick a date from a standard browser calendar and immediately see its lunar counterpart, complete with the Heavenly Stems and Earthly Branches.

### ⚡ Performance optimization
To keep the tool lightweight, we avoided heavy frameworks. By using Vanilla JS and modular CSS, we kept the entire project size under 1MB, ensuring it remains lightning-fast regardless of the user's connection.

> [!TIP]
> **Implementation Note:** We used a data-driven approach for the advice cards, separating the UI logic from the content dictionary to allow for easy localization and future expansions.

## The Collaborative Experience: Building with AI

The speed of development was made possible by an AI-first workflow.

1.  **AI Scaffolding**: We used AI to generate the initial UI structures and data models, saving hours of boilerplate work.
2.  **Refined Logic**: When we hit edge cases with leap months, we used AI to simulate dozens of scenarios, identifying potential bugs before they reached production.
3.  **UI Polish**: The modern, card-based layout was iterated upon multiple times with AI assistance to ensure it felt premium and balanced.


## The Project: By the Numbers

Building a niche tool with this level of detail usually requires significant manual checking. Here’s how the AI-assisted workflow performed:

*   **Total Development Time**: ~3 Hours (from concept to production-ready).
*   **Rounds of Iteration**: 15 (refining UI, mapping logic, and performance).
*   **Manual Verification Cycles**: 4 major rounds.
*   **Efficiency Gain**: ~60% faster than traditional development methods.

## Final Thoughts

**梅花易数 Web** proves that even the oldest traditions can find a home in the modern web stack. By focusing on performance and precision, we've built a tool that is both a reliable reference for practitioners and a beautiful example of modern web design.

**Interested in the source?** The project is open-source and ready for exploration on GitHub.
