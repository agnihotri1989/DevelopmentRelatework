# Block 8 Prompt — Smart Analytics (useMemo & Derived State Dashboard)

Ye prompt naye chat session mein copy-paste karein. Ye Block 8 ko start karega.

---

## Prompt (Copy karo 👇)

```
/performance-optimization

Main React Native project "TaskMatrix" (Smart Todo App with Local Analytics) build kar raha hun.
Mera background Android development (Kotlin/Java, Jetpack Compose, LiveData/StateFlow derived state) mein hai. Maine Block 0 se lekar Block 7 (UI layout, Flexbox, FlatList, useTodos custom hook, AsyncStorage persistence, aur React Navigation with Bottom Tabs) successfully complete kar liye hain.

📋 Complete Plan: /Users/kshitizagnihotri/Project/TaskMatrix/PLAN.md
📋 Skills reference: /Users/kshitizagnihotri/Project/TaskMatrix/Skills.md

---

## Aaj ka Goal: Block 8 — Smart Analytics & Memoization (useMemo Hook & Analytics Dashboard)

Ab tak hamare paas navigation setup ho gaya hai aur `AnalyticsScreen.js` ek placeholder thi. Block 8 mein hum real-time local analytics calculations implement karenge with performance optimization:

1. **`useMemo` Deep Dive & Memoization Concept:**
   - Memoization kya hai? Expensive computation ko har re-render par execute karne se kaise bachein?
   - Syntax: `const memoizedVal = useMemo(() => computeSomething(data), [dependency])`.
   - Kab use karna chahiye aur kab premature optimization avoid karni chahiye?
   - Android comparison:
     - Compose: `val stats by remember(todos) { derivedStateOf { calculateStats(todos) } }`
     - Android Architecture: `Transformations.map(todosLiveData) { ... }` ya StateFlow `.map { ... }`.
2. **Analytics Calculations Engine (`src/hooks/useAnalytics.js`):**
   - Todos array se derived stats calculate karna:
     - `totalTodos`: Total tasks count.
     - `completedTodos`: Completed count.
     - `pendingTodos`: Pending count.
     - `completionRate`: Percentage (e.g. 75%).
     - `categoryBreakdown`: Work, Personal, Health mein kitne tasks hain aur kitne complete hain.
   - `useMemo` se wrap karna taaki jab tak `todos` array change na ho, calculation zero CPU cycles le.
3. **Analytics Dashboard UI (`src/screens/AnalyticsScreen.js`):**
   - Block 2 mein banaya gaya reusable component `StatCard.js` reuse karna:
     - Card 1: Total Tasks (e.g. Blue badge).
     - Card 2: Completed Tasks (e.g. Green badge).
     - Card 3: Completion Rate % (with mini progress bar indicator).
   - Category Breakdown section render karna (FlatList ya map se category progress bars / counts dikhana).
   - Empty state view: Jab koi todo na ho ("No analytics available yet! Add some tasks.").
4. **End-to-End Verification:**
   - Todo add / complete / delete karke Analytics tab switch karke verify karna ki stats instantly aur accurately reflect hote hain.

---

## Mentorship & Rules:
- **Lego approach:** Step-by-step building. Pehle `useMemo` ka mental model aur Android analogy samajhna, phir `useAnalytics.js` hook likhna, phir `AnalyticsScreen.js` UI assemble karna.
- **What, Why, How:** Har concept ke liye clear breakdown.
- **Android/Kotlin Analogies:** `useMemo` ko Compose ke `remember(keys) { derivedStateOf { ... } }` se link karke samjhana.
- **Mentor Mode (Strict):** Agent sirf guide karega, performance trade-offs aur memoization pitfalls samjhayega, aur test steps batayega. Agent code direct write nahi karega jab tak main explicit allow na karun. Code main khud type karunga.
- **Checkpoint Verification:** Block 8 tabhi complete hoga jab:
  - [ ] `useMemo` ka working mechanism aur dependency array rule crystal clear ho.
  - [ ] `useAnalytics.js` pure derived state expose kare bina unnecessary re-computations ke.
  - [ ] `AnalyticsScreen.js` par real data ke saath StatCards aur category breakdown display ho.
  - [ ] Tasks toggle ya delete karne par analytics immediately update ho.

Shuru karein:
1. Pehle `useMemo` hook ka concept (What, Why, How + Android derivedStateOf analogy) aur calculation logic explain karein.
2. Phir mujhe step-by-step guide karein ki `src/hooks/useAnalytics.js` kaise craft karna hai aur use `AnalyticsScreen.js` mein kaise bind karna hai.
```

---

## Kaun sa Skill use karna hai?

Block 8 ke liye [Skills.md](file:///Users/kshitizagnihotri/Project/TaskMatrix/Skills.md) ke hisaab se:

| Skill | Category | Kyun use karein? |
|-------|----------|------------------|
| **`performance-optimization`** | **Primary (Recommended)** | Block 8 computation caching (`useMemo`), unnecessary re-render prevention, data memoization, aur efficient derived state metrics par focused hai. |
| **`frontend-ui-engineering`** | **Supporting** | `AnalyticsScreen.js` ke layout, StatCard reuse, aur progress indicators ko visual polish dene ke liye. |
| **`api-and-interface-design`** | **Supporting** | `useAnalytics` hook ke returned object contract ko clean aur predictable rakhne ke liye. |
