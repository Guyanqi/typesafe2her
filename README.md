# 🛡️ Type Safe to Her — User Guide

This tool uses **TypeSafe AI** to evaluate text messages sent in relationships. It scores proposed text messages across structured output decision types (`noul`, `score`, and `choice`) to prevent unintended arguments or misunderstandings.

---

## 📊 Evaluation Criteria Breakdown

### 1. `noul` Criteria (Continuous Probability: 0.0 to 1.0)
* **`dismissiveness_risk`**: Measures if the reply is low-effort or uses one-word brush-offs (`k`, `fine`, `whatever`).
* **`trap_answer_risk`**: Evaluates whether a question requires emotional reassurance, but the draft responds with literal logic.
* **`sarcasm_leak_risk`**: Detects if playful jokes or dry humor will sound mean or condescending when read without tone of voice.

### 2. `score` Criteria (Numeric Scale: 1 to 10)
* **`couch_sleep_index`**: Rates overall risk from **1** (Comfy bed together) to **10** (Sleeping on the couch tonight).
* **`emotional_effort_score`**: Rates effort and affection from **1** (Robotic/cold) to **10** (Golden Retriever warmth).

### 3. `choice` Criteria (Categorical Verdicts)
* **`perceived_emotion`**: How she will likely interpret your mood (`Loving`, `Passive-Aggressive`, `Ignoring me`, `Overly Logical`).
* **`overall_judgement`**: `🟢 GREEN LIGHT`, `🟡 YELLOW LIGHT`, or `🔴 RED LIGHT`.
* **`actionable_advice`**: Recommended correction strategy before sending.

---

## ⚔️ Comparison Examples: Safe vs. Unsafe Answers

### Scenario 1: The Loaded Question
> **Her Question:** *"Be honest, do you think I've gained weight recently?"*

* 🔴 **UNSAFE (High Danger / Trap Risk):**
  > `"A little bit, but honestly you still look fine to me and we can go to the gym together!"`
  * **Evaluation:** High `trap_answer_risk` (0.98), High `couch_sleep_index` (10/10), `RED LIGHT`. (Fails to realize this is an insecurity check requiring reassurance, not an analytical health evaluation).

* 🟢 **SAFE:**
  > `"What?? You look absolutely amazing as always! Stop overthinking, I love you so much ❤️"`
  * **Evaluation:** Low `trap_answer_risk` (0.02), High `emotional_effort_score` (9/10), `GREEN LIGHT`.

---

### Scenario 2: What to Eat for Dinner
> **Her Question:** *"What do you want to eat tonight?"*

* 🔴 **UNSAFE (Dismissive Risk):**
  > `"Whatever, I don't care, you pick."`
  * **Evaluation:** High `dismissiveness_risk` (0.88), Perceived as: *He's uninterested*, `YELLOW/RED LIGHT`.

* 🟢 **SAFE:**
  > `"I'm down for anything! How about sushi or Mexican? I can pick it up on my way back ❤️"`
  * **Evaluation:** Low `dismissiveness_risk` (0.05), High `emotional_effort_score` (8/10), `GREEN LIGHT`.

---

### Scenario 3: Bad Day at Work
> **Her Statement:** *"My boss gave me extra work 5 minutes before logging off, I'm so annoyed!"*

* 🔴 **UNSAFE (Overly Logical):**
  > `"Did you try telling him that your shift was over? You need to set better boundaries at work."`
  * **Evaluation:** "Of course I know what to do at work, I just want you to comfort me, but you can't even mind to say some sweet word", Low empathy, `YELLOW LIGHT`.

* 🟢 **SAFE:**
  > `"That is so unfair! You worked so hard today. Come home, I'll make tea and you can talk to me about it."`
  * **Evaluation:** High `emotional_effort_score` (10/10), Perceived as: *Loving & Attentive*, `GREEN LIGHT`.
