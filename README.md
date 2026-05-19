# Rule-Based-AI-Chatbot
### Project 1 | Industrial Training Kit | Batch 2026

![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![AI](https://img.shields.io/badge/AI-Rule--Based-1D9E75?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-success?style=for-the-badge)
![DecodeLabs](https://img.shields.io/badge/DecodeLabs-Batch%202026-0F6E56?style=for-the-badge)

---

## Live Demo
http://172.19.192.1:8080/Rule-Based%20AI%20Chatbot.html

## 📌 Overview

This is **Project 1** of the DecodeLabs AI Industrial Training Kit — a **Rule-Based AI Chatbot** built from scratch using Python. It demonstrates the foundational concepts of Artificial Intelligence through deterministic, logic-driven programming — before advancing to machine learning or deep learning systems.

> _"Before you build systems that learn on their own, you must master the art of teaching a machine through explicit if-else instructions."_
> — DecodeLabs

---

## 🎯 Project Goal

Build a simple rule-based chatbot that:
- Responds to **predefined user inputs** using a knowledge base
- Handles **greetings and exit commands**
- Uses **if-else / dictionary logic** for responses
- Runs in a **continuous loop** until the user exits

---

## 🧠 Core Concepts Covered

| Concept | Description |
|---|---|
| **Control Flow** | `while` loops, `if-elif-else` branching |
| **Input Sanitization** | `.lower().strip()` for normalization |
| **Data Structures** | Python dictionary as a knowledge base |
| **Algorithmic Efficiency** | O(1) dictionary lookup vs O(n) if-elif ladder |
| **IPO Model** | Input → Process → Output architecture |
| **AI Guardrails** | Rule-based filtering as a deterministic layer |

---

## 🏗️ Architecture — The IPO Model

```
┌─────────────────────────────────────────────────────┐
│                   USER INPUT                        │
│              (Raw, uncleaned text)                  │
└──────────────────────┬──────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────┐
│              PHASE 1: SANITIZATION                  │
│         raw_input = input("You: ")                  │
│         clean_input = raw_input.lower().strip()     │
└──────────────────────┬──────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────┐
│              PHASE 2: PROCESS                       │
│         Intent Matching via Dictionary O(1)         │
│         reply = responses.get(clean_input,          │
│                 "I do not understand.")             │
└──────────────────────┬──────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────┐
│              PHASE 3: OUTPUT                        │
│         Response Generation + Feedback Loop         │
│         print(f"Bot: {reply}")                      │
└─────────────────────────────────────────────────────┘
```

---

## 📋 Project Specification — The Logic Skeleton

- [x] **INPUT LOOP** — Continuous `while True` cycle
- [x] **SANITIZATION** — Handle case & whitespace with `.lower().strip()`
- [x] **KNOWLEDGE BASE** — Dictionary with 5+ intents
- [x] **FALLBACK** — Default response for unknown inputs
- [x] **EXIT STRATEGY** — Clean `break` command on "bye" / "exit"

---

## 📁 Project Structure

```
decodelabs-chatbot-p1/
│
├── chatbot.py              # Main Python chatbot script
├── chatbot_gui.html        # Web-based GUI version (bonus)
├── README.md               # This file
└── requirements.txt        # Dependencies (none for core version)
```

---

## 🐍 Python Implementation

```python
# DecodeLabs — Project 1: Rule-Based AI Chatbot
# Batch 2026 | Powered by DecodeLabs

# ─────────────────────────────────────────
# KNOWLEDGE BASE — Dictionary (O(1) lookup)
# ─────────────────────────────────────────
responses = {
    "hello"         : "Hi there! Welcome to DecodeLabs! 👋",
    "hi"            : "Hello! I'm your Rule-Based AI assistant.",
    "hey"           : "Hey! What can I help you with today?",
    "how are you"   : "I'm running perfectly — no bugs today! 😄",
    "what is ai"    : "AI is the simulation of human intelligence by machines!",
    "what is ml"    : "Machine Learning is AI that learns from data automatically.",
    "who made you"  : "I was built by a DecodeLabs intern — Batch 2026!",
    "tell me a joke": "Why do programmers prefer dark mode? Light attracts bugs! 🐛",
    "fun fact"      : "ELIZA (1966) was the first chatbot — also rule-based, just like me!",
    "help"          : "Try: hello, what is ai, tell me a joke, fun fact, bye",
    "thank you"     : "You're welcome! Happy coding! 😊",
    "thanks"        : "Anytime! Keep building! 💪",
    "bye"           : "Goodbye! Keep building amazing AI! 👋",
    "goodbye"       : "See you next time! Complete Project 1! 🛡️",
    "exit"          : "Session ended. Goodbye! 🚀",
}

# ─────────────────────────────────────────
# FALLBACK — Default response for unknowns
# ─────────────────────────────────────────
FALLBACK = "I don't understand that yet. Try typing 'help'!"

# ─────────────────────────────────────────
# MAIN LOOP — The Heartbeat
# ─────────────────────────────────────────
print("=" * 45)
print("   DecodeLabs AI Chatbot — Project 1")
print("   Type 'bye' or 'exit' to quit")
print("=" * 45)

while True:
    # PHASE 1: INPUT & SANITIZATION
    raw_input_text = input("\nYou: ")
    clean_input = raw_input_text.lower().strip()

    # EXIT STRATEGY
    if clean_input in ["bye", "goodbye", "exit", "quit"]:
        print("Bot:", responses.get(clean_input, "Goodbye! 👋"))
        break

    # PHASE 2: PROCESS — O(1) Dictionary Lookup
    reply = responses.get(clean_input, FALLBACK)

    # PHASE 3: OUTPUT
    print("Bot:", reply)
```

---

## ⚙️ How to Run

### Prerequisites
- Python 3.8 or higher

### Steps

```bash
# 1. Clone the repository
git clone https://github.com/yourusername/decodelabs-chatbot-p1.git

# 2. Navigate to the project directory
cd decodelabs-chatbot-p1

# 3. Run the chatbot
python chatbot.py
```

### Example Session

```
=============================================
   DecodeLabs AI Chatbot — Project 1
   Type 'bye' or 'exit' to quit
=============================================

You: hello
Bot: Hi there! Welcome to DecodeLabs! 👋

You: what is ai
Bot: AI is the simulation of human intelligence by machines!

You: tell me a joke
Bot: Why do programmers prefer dark mode? Light attracts bugs! 🐛

You: bye
Bot: Goodbye! Keep building amazing AI! 👋
```

---

## 📊 Algorithmic Efficiency — Why Dictionary over If-Elif?

```
Time to Execute
│
5s ─ ┤                                    ▲ If-Elif O(n)
     │                                 ╱
1s ─ ┤                           ╱
     │                      ╱
0s ─ ┤ ●━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ Dictionary O(1)
     └────────────────────────────────────────────────────
      0          100        1000       10000
                    Number of Rules
```

| Method | Time Complexity | Maintenance | Scalability |
|---|---|---|---|
| If-Elif Ladder | O(n) — Linear | High debt | Poor |
| Dictionary `.get()` | O(1) — Constant | Low debt | Excellent |

---

## 🔑 Key Design Patterns Used

### 1. The White Box Principle
Rule-based systems are fully transparent:
- **Traceability** — Input → Logic → Output. No mystery.
- **Safety** — Zero hallucination risk. 100% hard-coded.
- **Compliance** — Essential for Finance & Healthcare domains.

### 2. The `.get()` Method — Professional Approach
```python
# ❌ Anti-pattern: If-Elif Ladder (O(n), high technical debt)
if clean_input == "hello":
    reply = "Hi there!"
elif clean_input == "bye":
    reply = "Goodbye!"
elif clean_input == "help":
    reply = "Try: hello, bye..."
# ... 20 more elif blocks

# ✅ Professional: Dictionary Lookup (O(1), clean & scalable)
reply = responses.get(clean_input, "I do not understand.")
```

### 3. Input Sanitization
```python
# Handles: "Hello", "HELLO", "  hello  ", "Hello!" → "hello"
clean_input = raw_input_text.lower().strip()
```

---

## 🚀 Enhancement Ideas

Want to go beyond the baseline? Try these:

- [ ] **Expand vocabulary** — Add 20+ more intents to the dictionary
- [ ] **Keyword matching** — Respond even when input contains the keyword
- [ ] **Nested conditions** — Multi-turn conversations with state tracking
- [ ] **Personality** — Give the bot a unique name and character
- [ ] **Logging** — Save conversation history to a `.txt` file
- [ ] **Hybrid mode** — Route unmatched inputs to an LLM API

---

## 🏛️ The Two Minds of AI

This project teaches the **Deterministic** side of AI:

| System | Type | Description |
|---|---|---|
| **System 1 — The Artist** | Probabilistic | Neural networks, LLMs, generative AI |
| **System 2 — The Engineer** | Deterministic | Rule-based logic, guardrails, compliance |

> _"Before you can manage the chaos of a probability engine, you must master the precision of a logic engine."_

---

## Author
Hiba Sharif 

## 📄 License

This project is part of the DecodeLabs Industrial Training Program.
© 2026 DecodeLabs. All rights reserved.

---

> _"An LLM without rules is a hallucination engine. Today, we build the skeleton that holds the intelligence."_
> — DecodeLabs, Project 1
