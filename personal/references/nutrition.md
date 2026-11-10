# Nutrition: working alongside the dietitian

## Contents
- Scope rule
- Activation: the dietitian question
- Importing the dietitian's plan
- Daily routine: remind, ask, log
- Estimating what was eaten (photo, label, description)
- Known meals: learning over time
- Comparing with the plan (when the person asks)
- Training and food
- Without a dietitian
- Food reference table

## Scope rule

- **The dietitian prescribes the diet.** The agent **organizes, reminds, logs, estimates and compares** with the dietitian's plan. It does not change quantities, does not create menus, does not suggest supplements or doses on its own.
- Questions about swapping foods, eating off-plan, hunger, low energy, digestion, supplements: answer with what the **plan already allows** (its substitution list) and, if the plan does not cover it, note it for the person to bring to the dietitian.
- Before each appointment with the dietitian, offer a **summary of the period** (adherence, averages, difficulties, training performance) for the person to bring.

## Activation: the dietitian question

At intake, ask: **"Do you work with a dietitian?"**
- **Yes:** activate this module. Ask for the **meal plan** (PDF, photo of the sheet, app screenshot or text), the dietitian's name and the plan date. Also ask the real times of their routine (wake-up, work, training, sleep).
- **No:** do not count or track the diet. Follow the "Without a dietitian" section.
- Record the answer in the profile and ask again at the quarterly reassessment.

## Importing the dietitian's plan

1. Read the whole file or image.
2. Transcribe it into `clients/<name>/nutrition/meal-plan.md` using `templates/meal-plan.md`: meals, times, foods and quantities for each option, allowed substitutions, water, prescribed supplements, notes.
3. If the plan gives daily targets (calories, protein, carbohydrate, fat, fiber), copy them exactly. If it does not, calculate **approximate totals** for each meal using labels and the reference table, and mark them as **"estimated by the agent"**.
4. **Show the transcription to the person and ask for confirmation** before using it. Fix whatever they point out.
5. Keep the original file in the `nutrition/` folder, if possible. When the dietitian sends a new plan, replace it and note the date.

## Daily routine: remind, ask, log

**Reminders at meal times:**
- If the platform has **scheduled tasks or reminders** (for example the scheduled tasks of the Claude app), offer to create one reminder per meal in the plan, with the question ready ("10am: did you have your morning snack? yogurt + fruit"). Only create them with the person's "yes".
- If not, do the check **when the person opens the conversation**: look at the current time and ask, in one block, about the meals that should already have happened ("Good morning! Did you have breakfast? And the post-workout whey?").
- At the gym, remind the **pre-workout** meal on arrival (if in the plan) and the **post-workout** meal at the end of the session.

**Logging:** for each meal, accept the easiest answer for the person:
- "ate the same as the plan" or "plan option 2" → log the plan's values;
- photo of the plate, label or description → estimate (next section);
- "didn't eat" or "ate something else" → log it without judgment.

Save in `clients/<name>/nutrition/diary/YYYY-MM.md` (template `templates/food-diary.md`). Do not interrupt training with diet questions: in the middle of the sets, only the essentials.

## Estimating what was eaten (photo, label, description)

1. **Identify** each food and how it was prepared (grilled, fried, breaded, with sauce). Frying and sauces hide fat; ask if in doubt.
2. **Estimate the portion** with visual references:
   - a standard dinner plate is ~22 to 26 cm;
   - palm of the hand (no fingers) ≈ 100 to 120 g of cooked meat or chicken;
   - closed fist ≈ 1 cup (~150 to 160 g of cooked rice);
   - cupped hand ≈ half a cup of carbohydrate;
   - thumb ≈ 1 tablespoon of fat (olive oil, peanut butter).
   - 1 heaped tablespoon of cooked rice ≈ 25 g; 1 medium ladle of beans ≈ 100 to 140 g.
3. **Labels:** use the nutrition facts on the label and the portion the person ate; it is the most reliable data.
4. **Scale:** if the person weighs their food, use the weight; it is the best way to calibrate.
5. **Answer with a range and confidence:** "~550 to 650 kcal, ~40 g protein (medium confidence: I don't know if the chicken was fried)". Ask at most 1 quick question to refine.
6. **Expected error:** photo estimates easily miss by 20 to 30%. Say so once and improve over time through known meals.

## Known meals: learning over time

When a meal repeats ("my usual breakfast", "the chicken lunchbox"), record it in `clients/<name>/nutrition/known-meals.md` with the ingredients, quantities and values **confirmed by the person** (scale, label or plan). Next time, "had my usual breakfast" already has the right value. Correct it whenever the person says they changed something.

## Comparing with the plan (when the person asks)

The person asked for comparisons **when they ask**; do not produce a daily report unprompted. When asked:
- **Day:** meals done vs planned; estimated totals vs targets (calories, **protein** first, carbohydrate, fat, water); what was missing or in excess.
- **Week:** daily average vs target; days within target (±10%); average protein; adherence by meal (which one fails most); patterns ("on training days the afternoon snack disappears").
- Show it in a short table, with no sermon. Suggest adjustments **only within the plan** (e.g., "the plan allows swapping the snack for yogurt + whey, which is more practical at the gym"). Anything outside the plan becomes a question for the dietitian.
- Include a weekly summary in the check-in, if the person wants.

## Training and food

- Follow the plan's **pre- and post-workout times**. If the person is going to train a long time after the last meal (over 3 to 4 h) and the plan has nothing for it, note it to ask the dietitian.
- **Hydration:** drink water through the day and during training; the water target is the plan's. Clear urine is a good sign.
- Signs to bring to the dietitian: low energy in workouts, performance drop over several sessions, dizziness, excessive hunger, frequent cramps, trouble recovering, weight change outside what is expected.

## Without a dietitian

Do not build a menu, count calories or suggest supplements. You may give only general health guidance: meals with some protein source, fruits and vegetables; drink water; do not train fasted for a long time if it causes discomfort; sleep well. Recommend seeing a dietitian, explaining that she is the one who adjusts food to the goal.

## Food reference table (approximate values)

Based on common food-composition tables and typical labels. **Always prefer the dietitian's plan and the product label.**

| Food | Portion | kcal | Protein (g) | Carbohydrate (g) | Fat (g) |
|---|---|---|---|---|---|
| White rice, cooked | 100 g | 128 | 2.5 | 28 | 0.2 |
| Brown rice, cooked | 100 g | 124 | 2.6 | 26 | 1 |
| Brazilian carioca beans, cooked | 100 g | 76 | 4.8 | 14 | 0.5 |
| Pasta, cooked | 100 g | ~150 | 5 | 30 | 1 |
| Potato, boiled | 100 g | 52 | 1.2 | 12 | 0 |
| Sweet potato, boiled | 100 g | 77 | 0.6 | 18 | 0.1 |
| Cassava, boiled | 100 g | 125 | 0.6 | 30 | 0.3 |
| Bread roll (French style) | 1 unit (50 g) | 150 | 4 | 29 | 1.5 |
| Rolled oats | 30 g | 118 | 4 | 20 | 2.6 |
| Banana | 1 medium (~70 g) | ~70 | 0.9 | 18 | 0 |
| Apple | 1 medium (~130 g) | ~70 | 0.4 | 20 | 0 |
| Papaya | 100 g | 40 | 0.5 | 10 | 0.1 |
| Egg, boiled | 1 unit (50 g) | 73 | 6.6 | 0.3 | 4.8 |
| Egg white | 1 unit (~33 g) | 17 | 3.6 | 0.2 | 0 |
| Grilled chicken breast | 100 g | 159 | 32 | 0 | 2.5 |
| Grilled lean beef (round) | 100 g | 219 | 36 | 0 | 7.3 |
| Grilled tilapia | 100 g | ~128 | 26 | 0 | 2.7 |
| Grilled salmon | 100 g | ~230 | 24 | 0 | 14 |
| Canned tuna in water (drained) | 100 g | ~116 | 26 | 0 | 1 |
| Whole milk | 200 ml | 122 | 6.4 | 9.4 | 6.6 |
| Skim milk | 200 ml | ~70 | 6.8 | 9.8 | 0.4 |
| Fresh white cheese | 30 g | 79 | 5.2 | 1 | 6 |
| Mozzarella | 30 g | 99 | 6.8 | 1 | 7.6 |
| Whey protein (check the label) | 30 g | 110 to 130 | 20 to 25 | 2 to 5 | 1 to 2 |
| Peanut butter | 15 g | ~90 | 4 | 3 | 7.5 |
| Brazil nut | 1 unit (~4 g) | ~26 | 0.6 | 0.5 | 2.6 |
| Olive oil or cooking oil | 1 tablespoon (~10 to 13 g) | 90 to 120 | 0 | 0 | 10 to 13 |
| Sugar | 1 teaspoon (5 g) | 20 | 0 | 5 | 0 |

Rule of thumb: protein and carbohydrate have ~4 kcal per gram; fat, ~9 kcal per gram.
