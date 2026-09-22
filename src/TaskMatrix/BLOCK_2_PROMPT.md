# Block 2 Prompt — Styling Mastery (StyleSheet.create, Flexbox & Dynamic Styling)

Ye prompt naye chat session mein copy-paste karein. Ye Block 2 ko start karega.

---

## Prompt (Copy karo 👇)

```
/frontend-ui-engineering

Main React Native project "TaskMatrix" (Smart Todo App with Local Analytics) build kar raha hun.
Mera background Android development (Kotlin/Java, Jetpack Compose, XML layout) mein hai. Maine Block 0 (JS/ES6) aur Block 1 (JSX, View, Text, App.js setup) complete kar liya hai.

📋 Complete Plan: /Users/kshitizagnihotri/Project/TaskMatrix/PLAN.md
📋 Skills reference: /Users/kshitizagnihotri/Project/TaskMatrix/Skills.md

---

## Aaj ka Goal: Block 2 — Styling Mastery (StyleSheet.create & Dynamic Styling)

Mujhe React Native ka layout system aur styling deeply seekhna hai:

1. **`StyleSheet.create` vs Inline Styles:**
   - Why StyleSheet over inline objects? (Performance, caching, validation)
   - Android comparison: `res/values/styles.xml` & theme attributes vs hardcoded layout attributes.
2. **Flexbox in React Native (Deep Dive):**
   - RN default: `flexDirection: 'column'` (Web par default 'row' hota hai)
   - `justifyContent` (main axis alignment) vs `alignItems` (cross axis alignment)
   - `flex: 1` vs Android `layout_weight="1"` / Compose `Modifier.weight(1f)`
   - Android comparison: `LinearLayout` (vertical/horizontal) + `ConstraintLayout`
3. **Dynamic / Conditional Styling:**
   - Style arrays: `style={[styles.base, isCompleted && styles.completed]}`
   - Dynamic inline values based on props
4. **Hands-on Building:**
   - App colors & theme constants (`src/utils/constants.js` ya theme setup)
   - Header styling polish in `App.js`
   - Reusable `StatCard.js` component with dynamic colors & styles (`src/components/StatCard.js`)

---

## Mentorship & Rules:
- **Lego approach:** Step-by-step building. Pehle concepts samajhna, phir code likhna.
- **What, Why, How:** Har concept ke liye clear structure.
- **Android/Kotlin Analogies:** Flexbox properties ko LinearLayout/weight/Gravity se compare karke samjhana.
- **Mentor Mode (Strict):** Agent sirf guide karega, code structure explain karega, aur verification mein help karega. Agent code tab tak direct write nahi karega jab tak main explicit allow na karun. Code main khud type karunga.
- **Checkpoint Verification:** Block 2 ke criteria verify hone ke baad hi complete declare karenge:
  - [ ] `flexDirection`, `justifyContent`, `alignItems` clear hain?
  - [ ] Style array `[styleA, condition && styleB]` pattern samajh aaya?
  - [ ] Reusable `StatCard` render ho kar dynamic style demonstrate kar raha hai?

Shuru karein:
1. Pehle `StyleSheet.create` aur Flexbox ka concept (What, Why, How + Android analogy) explain karein.
2. Phir mujhe step-by-step batayein ki layout test karne aur theme/components build karne ke liye mujhe kya code likhna hai.
```

---

## Kaun sa Skill use karna hai?

Block 2 ke liye [Skills.md](file:///Users/kshitizagnihotri/Project/TaskMatrix/Skills.md) ke hisaab se:

| Skill | Category | Kyun use karein? |
|-------|----------|------------------|
| **`frontend-ui-engineering`** | **Primary (Recommended)** | Block 2 styling, design tokens/theme, flexbox layout, aur reusable `StatCard` component architecture par focused hai. Ye skill modern responsive UI, clean styling rules aur component patterns ke liye exact match hai. |
| **`context-engineering`** | **Alternative / Session Init** | Project background, rules aur progress trace load karne ke liye. |
| **`code-simplification`** | **Supporting (Later in block)** | Complex styles ya nested Flexbox hierarchy ko clean aur readable rakhne ke liye. |
