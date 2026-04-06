---
description: Get personalized nutrition guidance for training and daily eating
argument-hint: [topic, e.g. "race day fueling" or "recovery meal ideas" or "daily macros"]
---

Help the athlete with nutrition for cycling performance. This covers both on-bike fueling and daily nutrition tailored to their training load.

## Step 1: Understand the Context

If `$ARGUMENTS` specifies a topic, focus on that. Otherwise, ask what the athlete needs help with using AskUserQuestion:

- Ride fueling (what to eat/drink before, during, after rides)
- Daily nutrition and macros for their current training phase
- Race or event day nutrition planning
- Body composition goals alongside training

## Step 2: Pull Training Data

Retrieve from Intervals.icu:

- Recent activities (last 7 days) — to understand current training volume and intensity
- Current fitness summary (CTL, ATL) — to gauge overall training load
- Wellness data — weight trends, any logged nutrition data
- Athlete profile — current FTP, weight

## Step 3: Ask About Goals and Constraints

Use AskUserQuestion to learn what's relevant (skip questions the athlete has already answered or that aren't relevant to their specific request):

- **Nutrition goals**: Are you trying to fuel performance, lose weight while maintaining power, or both?
- **Dietary constraints**: Any allergies, intolerances, or dietary preferences? (e.g., vegetarian, lactose intolerant, gluten-free)
- **Practical constraints**: Do you cook meals yourself? Do you meal prep? Any time or budget constraints?
- **Current habits**: What does a typical training day of eating look like for you right now?
- **Supplements**: Are you currently using any sports nutrition products (gels, drink mix, bars, caffeine)?

## Step 4: Provide Personalized Guidance

Based on the athlete's data and answers, provide specific, actionable advice. Always tie nutrition recommendations back to their actual training numbers. Reference the nutrition guidelines in `references/nutrition-guidelines.md` for baseline values, then personalize.

### For Ride Fueling

- **Pre-ride**: What to eat and when, based on ride duration and intensity
- **During ride**: Carbs per hour targets based on ride intensity and duration (30-60g/hr for moderate rides, 60-90g/hr for hard/long rides, up to 90-120g/hr for elite-level efforts if gut-trained)
- **Post-ride**: Recovery nutrition window, protein and carb targets based on the session's TSS
- **Hydration**: Fluid and electrolyte guidance based on ride duration, intensity, and conditions

### For Daily Nutrition

- **Calorie estimates**: Based on training load (use kJ from recent activities to estimate daily expenditure)
- **Macro targets**: Protein (1.6-2.2g/kg for endurance athletes), carbs (periodized based on training day intensity), fat (remainder)
- **Periodized eating**: More carbs on hard training days, moderate on easy days, lower on rest days
- **Practical meal ideas**: Suggest concrete meals and snacks, not just macro numbers

### For Body Composition

- If the athlete wants to lose weight while training, recommend a modest deficit (200-300 kcal) on easy/rest days only
- Never recommend restricting fuel on hard training days — performance comes first
- Frame weight loss in terms of sustainable rate (0.3-0.5 kg/week max for athletes in training)
- Monitor power-to-weight ratio, not just scale weight

## Guidelines

- Be specific with quantities and timing, not vague ("eat some carbs" is not helpful — "eat 80-100g of carbs in the 2-3 hours before your ride" is)
- Always account for the athlete's dietary constraints and preferences
- If the athlete's goals conflict (e.g., lose weight fast while building FTP), explain the tradeoff honestly and recommend a balanced approach
- Reference their actual training data — a 1500 TSS week has very different nutrition needs than a 400 TSS recovery week
- Encourage the athlete to experiment and find what works for their gut, especially for on-bike nutrition
