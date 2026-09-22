# Block 6 Prompt — Data Persistence (AsyncStorage & auto-save)

Ye prompt naye chat session mein copy-paste karein. Ye Block 6 ko start karega.

---

## Prompt (Copy karo 👇)

```
/api-and-interface-design

Main React Native project "TaskMatrix" (Smart Todo App with Local Analytics) build kar raha hun.
Mera background Android development (Kotlin/Java, SharedPreferences/DataStore, Room) mein hai. Maine Block 0 se lekar Block 5 (UI, Flexbox, FlatList, useState, useEffect, useTodos custom hook) successfully complete kar liye hain.

📋 Complete Plan: /Users/kshitizagnihotri/Project/TaskMatrix/PLAN.md
📋 Skills reference: /Users/kshitizagnihotri/Project/TaskMatrix/Skills.md

---

## Aaj ka Goal: Block 6 — Local Data Persistence (AsyncStorage)

Ab tak app refresh ya close hone par hamare todos reset ho jaate hain. Block 6 mein hum offline persistence implement karenge:

1. **AsyncStorage Fundamentals & Architecture:**
   - AsyncStorage kya hai? (Asynchronous, unencrypted, persistent, key-value storage).
   - Limitation: Sirf string data type store karta hai -> `JSON.stringify()` (serialization) aur `JSON.parse()` (deserialization) zaroori hai.
   - Android comparison:
     - AsyncStorage = Android `SharedPreferences` (ya modern `Preferences DataStore`).
     - `JSON.stringify` / `parse` = Kotlin `Gson().toJson()` / `fromJson()`.
     - `async/await` = Kotlin Coroutines `withContext(Dispatchers.IO)`.
2. **Persistence Storage Module Design:**
   - Dedicated service layer banana: `src/storage/asyncStorage.js`.
   - Methods: `saveTodos(todos)`, `loadTodos()`, `clearTodos()`.
   - Error handling: `try/catch` with fallback values (return `[]` on error/null).
3. **Integration with `useTodos` Hook & Lifecycle:**
   - App launch pe load karna: `useEffect` with `[]` dependency array (Mount lifecycle).
   - Auto-save trigger: Todos update hone par automatically persist karna (`useEffect` with `[todos]`), ya mutating actions (`add`, `toggle`, `delete`) ke andar save call karna.
   - Initial load race condition avoid karna (empty initial state se saved data overwrite na ho jaye via loading flag / boolean ref).
4. **Hands-on Verification:**
   - New todo add karo, app ko reload karo (Metro terminal mein 'r' press karo ya phone shake karke reload karo).
   - Confirm karo ki data intact rehta hai.

---

## Mentorship & Rules:
- **Lego approach:** Step-by-step building. Pehle AsyncStorage mechanics aur JSON serialization samajhna, phir storage wrapper banana, phir hook mein seamlessly integrate karna.
- **What, Why, How:** Har concept ke liye clear breakdown.
- **Android/Kotlin Analogies:** Har concept ko SharedPreferences, Gson, aur Coroutines IO thread se compare karke samjhana.
- **Mentor Mode (Strict):** Agent sirf guide karega, syntax aur race conditions samjhayega, aur test checklist batayega. Agent code direct write nahi karega jab tak main explicit allow na karun. Code main khud type karunga.
- **Checkpoint Verification:** Block 6 tabhi complete hoga jab:
  - [ ] AsyncStorage ka async key-value model aur JSON serialization clear ho.
  - [ ] `src/storage/asyncStorage.js` separate utility ban jaye.
  - [ ] `useTodos` hook safely data load aur save kare (initial empty overwrite bug ko handle karte hue).
  - [ ] App reload karne par saved todos screen par visible rahein.

Shuru karein:
1. Pehle package install command aur AsyncStorage ka concept (What, Why, How + Android SharedPreferences analogy) explain karein.
2. Phir mujhe step-by-step guide karein ki `src/storage/asyncStorage.js` kaise likhna hai aur `useTodos.js` mein data persistence kaise wire-up karni hai.
```

---

## Kaun sa Skill use karna hai?

Block 6 ke liye [Skills.md](file:///Users/kshitizagnihotri/Project/TaskMatrix/Skills.md) ke hisaab se:

| Skill | Category | Kyun use karein? |
|-------|----------|------------------|
| **`api-and-interface-design`** | **Primary (Recommended)** | Block 6 data boundary aur storage contract design par focused hai — `src/storage/asyncStorage.js` ka clean API contract (`saveTodos`, `loadTodos`), serialization boundary, aur safe fallback error semantics define karne ke liye exact match hai. |
| **`debugging-and-error-recovery`** | **Supporting** | AsyncStorage integration mein aane wale classic edge-cases (jaise initial render par empty list ka saved storage ko overwrite kar dena, JSON parse errors, async race conditions) ko safely guard karne ke liye. |
| **`context-engineering`** | **Session Init** | Naye chat session mein project context aur rules initialize karne ke liye. |
