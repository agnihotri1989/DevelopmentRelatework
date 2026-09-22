# Block 3 Prompt — User Input (TextInput, TouchableOpacity & useState Intro)

Ye prompt naye chat session mein copy-paste karein. Ye Block 3 ko start karega.

---

## Prompt (Copy karo 👇)

```
/frontend-ui-engineering

Main React Native project "TaskMatrix" (Smart Todo App with Local Analytics) build kar raha hun.
Mera background Android development (Kotlin/Java, Jetpack Compose, XML layout) mein hai. Maine Block 0 (JS/ES6), Block 1 (JSX, View, Text), aur Block 2 (StyleSheet, Flexbox, Dynamic styles, StatCard) complete kar liya hai.

📋 Complete Plan: /Users/kshitizagnihotri/Project/TaskMatrix/PLAN.md
📋 Skills reference: /Users/kshitizagnihotri/Project/TaskMatrix/Skills.md

---

## Aaj ka Goal: Block 3 — User Input (TextInput, TouchableOpacity & useState Intro)

Mujhe user interaction aur React ke reactivity cycle ko deeply seekhna hai:

1. **`useState` Hook (Introductory Level):**
   - React state kya hai? Component re-render kaise trigger hota hai?
   - `const [text, setText] = useState('')` syntax breakdown (Array destructuring recap from Block 0).
   - Android comparison: Compose `var text by remember { mutableStateOf("") }` ya Android `MutableLiveData` / `StateFlow`.
2. **`TextInput` Component & Controlled Input Pattern:**
   - Props: `value`, `onChangeText`, `placeholder`, `onSubmitEditing`, keyboard types.
   - Controlled Component pattern: State drives the input value vs unmanaged input.
   - Android comparison: `EditText` with `addTextChangedListener` vs Compose `TextField(value = text, onValueChange = { text = it })`.
3. **`TouchableOpacity` Component:**
   - Touch feedback (`activeOpacity`), press events (`onPress`).
   - Android comparison: `Button` with ripple effect / `setOnClickListener` / Compose `clickable`.
4. **Hands-on Building:**
   - `src/components/TodoInput.js` component banana (input box + "+ Add" button).
   - Category selector chips / pill buttons (Work, Personal, Health) ka basic UI or selection state.
   - Input validation check (empty text prevent karna, submit hone par input clear karna).
   - `App.js` mein test karna (console log ya temporary state ke saath).

---

## Mentorship & Rules:
- **Lego approach:** Step-by-step building. Pehle concept samajhna, phir code likhna.
- **What, Why, How:** Har concept ke liye clear structure.
- **Android/Kotlin Analogies:** Har concept ko Android state, EditText aur onClick listener se compare karke samjhana.
- **Mentor Mode (Strict):** Agent sirf guide karega, code structure explain karega, aur verification test step batayega. Agent direct code file write nahi karega jab tak main explicit permission na doon. Code main khud type karunga.
- **Checkpoint Verification:** Block 3 tabhi complete hoga jab:
  - [ ] `[value, setValue] = useState(initial)` ka working cycle clear ho.
  - [ ] Controlled component ka concept clear ho (`value` + `onChangeText`).
  - [ ] `TodoInput.js` properly render ho, typing smooth chale, aur Add press karne par callback trigger ho kar input reset ho.

Shuru karein:
1. Pehle `useState`, `TextInput`, aur `TouchableOpacity` ka concept (What, Why, How + Android analogy) explain karein.
2. Phir mujhe step-by-step guide karein ki `TodoInput.js` component kaise structure aur code karna hai.
```

---

## Kaun sa Skill use karna hai?

Block 3 ke liye [Skills.md](file:///Users/kshitizagnihotri/Project/TaskMatrix/Skills.md) ke hisaab se:

| Skill | Category | Kyun use karein? |
|-------|----------|------------------|
| **`frontend-ui-engineering`** | **Primary (Best Fit)** | Block 3 interactable UI components (`TextInput`, `TouchableOpacity`), state flow (`useState`), form inputs, validation, aur accessibility/touch target standards cover karta hai. |
| **`context-engineering`** | **Supporting / Session Init** | Project background, rules aur progress maintain karne ke liye. |
| **`api-and-interface-design`** | **Supporting (Component Props)** | `TodoInput` component ke props contract (jaise `onAdd(text, category)`) ko clean aur decoupled design karne ke liye. |
