# 🏋️ Personal: a personal trainer agent for Claude

> **An idea by [JulianaFontanezzi](https://github.com/julianafontanezzi)**: turn Claude into a personal trainer that truly coaches you, workout by workout, month by month, including live during your session at the gym.

![Type](https://img.shields.io/badge/type-Claude%20skill-blue)
![Language](https://img.shields.io/badge/language-English-green)
![Status](https://img.shields.io/badge/status-evolving-orange)

---

## 💡 The idea

We have all been there: you download a workout plan from the internet, follow it for three months and never adjust it. Nobody remembers your load from last week, nobody asks how your shoulder felt, nobody knows what you like or hate doing.

**The idea behind this skill, created by JulianaFontanezzi, is simple and ambitious:** what if Claude could be your personal trainer, chatting with you *while you are at the gym*, remembering everything about you and adjusting your training over time?

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

You need a copy of the `personal` folder (the one that contains `SKILL.md`). Pick the way that matches how you use Claude.

### Step 0: get the files
1. On this page, click the green **Code** button and choose **Download ZIP**.
2. Unzip the downloaded file. Inside you will find a folder called `personal`. That is the skill.

### Option A: Claude app or claude.ai (no coding needed)
1. Make a `.zip` of the **`personal` folder itself**:
   - **Windows:** right-click the `personal` folder → **Send to** → **Compressed (zipped) folder**.
   - **macOS:** right-click the `personal` folder → **Compress "personal"**.
2. Open Claude and go to **Settings** → **Capabilities** (the menu may be called **Customize** in newer versions) → **Skills**.
3. Click **Upload skill** and choose the `personal.zip` file.
4. Make sure the **Personal** skill is switched **on**.

> The zip must contain the `personal` folder with `SKILL.md` directly inside it. If you zip the whole downloaded repository, the upload will not work. Skills may require a plan or a setting (such as code execution) to be enabled in your account; menu names can vary between versions.

### Option B: Claude Code (terminal)
Copy the `personal` folder into your skills folder:

- **For all your projects:**
  - **Windows:** `C:\Users\YOUR-USER\.claude\skills\personal`
  - **macOS / Linux:** `~/.claude/skills/personal`
- **For one project only:** `.claude/skills/personal` inside that project folder.

Close and reopen Claude Code so it loads the new skill.

### Check that it works
Start a new conversation and write: **"I want to start training, can we do my assessment?"** If the skill is active, Claude will start with a few safety questions (PAR-Q) instead of a generic answer. You can also ask Claude: *"Which skills do you have available?"*

### Make it remember you between conversations
The agent saves your profile, workouts, sessions and measurements as files in a `clients/` folder **inside the folder where you are working**. So:
1. Create one folder just for this, for example `my-personal`.
2. **Always** open Claude (or Claude Code) in that same folder.

If you work in a different folder each time, the agent will not find your history and will start from zero. Your data never leaves your computer through this repository, and the `clients/` folder is ignored by Git.

### Update or remove
- **Update:** download the new version and replace the `personal` folder (or upload the new zip). Your `clients/` folder is separate and is not touched.
- **Remove:** delete the `personal` folder from your skills folder, or switch the skill off in **Settings → Capabilities → Skills**.

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

**Original idea, concept and project direction: [JulianaFontanezzi](https://github.com/julianafontanezzi)**

The vision of an AI personal trainer that coaches you live at the gym, remembers your history and works together with your dietitian is the creation of JulianaFontanezzi.

If this project helped you, leave a ⭐ on the repository and tag JulianaFontanezzi when you share it.

---

## 📄 License

Released under the [MIT License](LICENSE). Copyright (c) 2026 JulianaFontanezzi. You are free to use, copy and modify this project, as long as the copyright notice and the license text are kept with it.
