# 🏋️ Personal: a personal trainer agent for Claude

> **An idea by [0xFONTA](https://github.com/0xFONTA)**: turn Claude into a personal trainer that truly coaches you, workout by workout, month by month, including live during your session at the gym.

![Type](https://img.shields.io/badge/type-Claude%20skill-blue)
![Language](https://img.shields.io/badge/language-English-green)
![Status](https://img.shields.io/badge/status-evolving-orange)

---

## 💡 The idea

We have all been there: you download a workout plan from the internet, follow it for three months and never adjust it. Nobody remembers your load from last week, nobody asks how your shoulder felt, nobody knows what you like or hate doing.

**The idea behind this skill, created by 0xFONTA, is simple and ambitious:** what if Claude could be your personal trainer, chatting with you *while you are at the gym*, remembering everything about you and adjusting your training over time?

That is how **Personal** was born: an agent that does not just "build a workout" but **runs a full coaching relationship**, the way a good professional would.

---

## ✨ What it does

| Situation | What the agent does |
|---|---|
| **First session** | Runs safety screening (PAR-Q), learns your goal, sports history, tastes, routine and equipment |
| **Live at the gym** | Asks how you arrived (sleep, energy, pain, time), shows last time's load, and after each set you send ("42.5 x 10, 2 left") it tells you whether to keep, raise or lower the load and how long to rest |
| **Technique questions** | Answers in 3 to 4 sentences: the main adjustment, how to feel the right muscle and the most common mistake. Has a guide for about 35 exercises and swaps for when equipment is taken |
| **Minor training pain** | Separates what is normal (burn, next-day soreness, cramps) from what needs adjusting. Uses a traffic light based on the pain score and adjusts the exercise by body region |
| **Nutrition** | *Only if you work with a dietitian:* asks for the plan, reminds you of meals and whey at the right times, logs what you ate from photos, labels or descriptions and compares it with the plan when you ask |
| **Check-in** | Every 1 to 2 weeks: adherence, loads, effort, pain, sleep and motivation, with clear progression rules |
| **Quarterly reassessment** | Every 3 months: measurements, photos, simple tests, a review of the quarter and a **new program** |

### 🧠 It remembers you

The agent keeps one folder per client with your **profile** (goals, sports history, tastes, what motivates and discourages you), **current workout**, a **log of every session**, your **measurements** and your **meal plan**. The more you use it, the better it knows you.

### 🛡️ Safety first

- **PAR-Q** screening before the first workout.
- A list of **signs to stop immediately** (chest pain, dizziness, unusual shortness of breath...).
- Effort measured in **reps in reserve (RIR)**, with "safe maximum" rules when there is no spotter.
- The agent **does not diagnose**, and does not prescribe diet, medication or supplements. The dietitian's plan is final.

---

## 📦 Repository contents

```
personal/
├── SKILL.md                      ← the "brain": the agent's coaching script
├── references/                   ← knowledge base
│   ├── programming.md            ← tension vs metabolic, max-effort sets, techniques
│   ├── beginners-and-splits.md   ← entry program and 2 to 6 day splits
│   ├── progression.md            ← when to raise load, deload, plateaus, missed sessions
│   ├── exercise-technique.md     ← exercise technique and swaps
│   ├── training-pain.md          ← muscle soreness and adjustments by region
│   ├── nutrition.md              ← working alongside a dietitian
│   ├── reassessment.md           ← measurements and review every 3 months
│   ├── assessment.md             ← intake and pain questions
│   ├── anatomy.md                ← muscles and their functions
│   ├── extras.md                 ← warm-up, cardio, sleep, motivation
│   ├── science-update.md         ← corrects outdated points
│   └── gym-floor-service.md      ← instructor conduct and client service
└── templates/                    ← ready-made forms (profile, workout, session, measurements, diet)
```

---

## 🚀 Installation

### Claude Code
1. Download or clone this repository:
   ```bash
   git clone https://github.com/0xFONTA/skill-personal-trainer.git
   ```
2. Copy the `personal` folder into the Claude Code skills folder:
   - **Windows:** `C:\Users\YOUR-USER\.claude\skills\personal`
   - **macOS / Linux:** `~/.claude/skills/personal`

### Claude app or website
1. Zip the `personal` folder into a `.zip` file (`SKILL.md` must sit inside the `personal` folder).
2. In the **Skills** area of the settings, upload the file.

> 💾 **Important tip:** for the agent to **remember you between conversations**, always use the **same working folder**. That is where it creates the `clients/` folder with your data. For example, create a folder called `my-personal` and always open Claude in it.

> 🌍 **Language:** the files are in English, but the agent replies in whatever language you write to it.

---

## 💬 How to use it

Once installed, just talk. A few ways to start:

- *"I want to start training, can we do my assessment?"*
- *"I'm at the gym, let's train!"*
- *"How do I do a stiff-leg deadlift properly? I feel it in my lower back."*
- *"My shoulder bothers me on bench press, what should I adjust?"*
- *"I have a dietitian. I'm going to send you my meal plan."*
- *"It's been 3 months, let's reassess my program and my measurements."*

---

## 🔒 Privacy

Client data (health, measurements, food) stays **only in the `clients/` folder on your computer**. It is listed in `.gitignore` and **must never be published**. If you contribute to this project, check before every commit that no personal data is going along.

---

## ⚠️ Important notice

This skill is a **support tool** and **does not replace** health professionals. It does not make medical diagnoses and does not prescribe diets, medications or supplements. Before starting any exercise program, seek guidance from a fitness professional and, if you have any health condition, a doctor. In case of chest pain, severe shortness of breath or fainting, **seek emergency care immediately.**

The content is based on widely shared strength-training knowledge and organized for educational use. It may contain inaccuracies: review it with a professional.

### Not covered yet
Pregnancy, frail older adults, heart disease, diabetes, hypertension, adolescents, chronic pain, power training and sport-specific work. For these cases the agent is conservative and recommends in-person guidance.

---

## 🗺️ Roadmap

- [ ] Protocols for special populations
- [ ] More exercises in the technique library
- [ ] In-depth cardio and weight-loss coaching
- [ ] Automated test cases for the agent
- [ ] Versions in other languages

Suggestions and contributions are very welcome! Open an *issue* or a *pull request*.

---

## 👤 Credits

**Original idea, concept and project direction: [0xFONTA](https://github.com/0xFONTA)**

The vision of an AI personal trainer that coaches you live at the gym, remembers your history and works together with your dietitian is the creation of 0xFONTA. The files were built with the help of [Claude](https://claude.com), following 0xFONTA's instructions and decisions throughout development.

If this project helped you, leave a ⭐ on the repository and tag 0xFONTA when you share it.

---

## 📄 License

*To be defined by 0xFONTA.* Suggestion: [MIT](https://choosealicense.com/licenses/mit/) (free use, keeping the credit) or [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) (free use with mandatory attribution).
