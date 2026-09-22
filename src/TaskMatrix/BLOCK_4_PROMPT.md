# Block 4 Prompt — Lists Done Right (ScrollView vs FlatList & TodoItem Component)

Ye prompt naye chat session mein copy-paste karein. Ye Block 4 ko start karega.

---

## Prompt (Copy karo 👇)

```
/frontend-ui-engineering

Main React Native project "TaskMatrix" (Smart Todo App with Local Analytics) build kar raha hun.
Mera background Android development (Kotlin/Java, Jetpack Compose, XML layout) mein hai. Maine Block 0 (JS/ES6), Block 1 (JSX, View, Text), Block 2 (StyleSheet, Flexbox, Dynamic styles), aur Block 3 (TextInput, TouchableOpacity, useState, TodoInput) successfully complete kar liye hain.

📋 Complete Plan: /Users/kshitizagnihotri/Project/TaskMatrix/PLAN.md
📋 Skills reference: /Users/kshitizagnihotri/Project/TaskMatrix/Skills.md

---

## Aaj ka Goal: Block 4 — Lists Done Right (ScrollView vs FlatList)

Mujhe React Native mein efficient list rendering deeply seekhna hai:

1. **`ScrollView` vs `FlatList` (Memory & Architecture):**
   - `ScrollView`: Saare child views ek saath render karta hai (Eager loading). Small static content ke liye accha hai.
   - `FlatList`: Windowing / Lazy loading — sirf on-screen items render karta hai, off-screen unmount karta hai.
   - Android comparison: `ScrollView` = Android `ScrollView` vs `FlatList` = Android `RecyclerView` / Compose `LazyColumn`.
2. **`FlatList` Core Props:**
   - `data`: Array of items.
   - `renderItem`: `({ item, index }) => <JSX />` (Compare with Android `onCreateViewHolder` + `onBindViewHolder`).
   - `keyExtractor`: `(item) => item.id.toString()` (Diffing algorithm ke liye stable unique keys, compare with Android `DiffUtil` / Compose `key`).
   - `ItemSeparatorComponent` & `ListEmptyComponent` (Empty states handle karna).
3. **Hands-on Building:**
   - `src/components/TodoItem.js` component:
     - Todo title, category badge, complete toggle checkbox/icon, delete button.
     - Dynamic styling: completed todo par strikethrough (`textDecorationLine: 'line-through'`) aur faded opacity.
   - `src/screens/HomeScreen.js` (ya `App.js` mein list integration):
     - Dummy list of todos render karke scroll behavior aur keyExtractor verify karna.
     - `TodoInput` aur `FlatList` ko ek saath assemble karna.

---

## Mentorship & Rules:
- **Lego approach:** Step-by-step building. Pehle concept samajhna, phir code likhna.
- **What, Why, How:** Har concept ke liye clear structure.
- **Android/Kotlin Analogies:** `FlatList` ko `RecyclerView` (ViewHolder, Adapter, DiffUtil) aur Compose `LazyColumn` se link karke samjhana.
- **Mentor Mode (Strict):** Agent sirf guide karega, code explain karega aur verify karega. Agent direct file write nahi karega jab tak main explicit allow na karun. Code main khud type karunga.
- **Checkpoint Verification:** Block 4 tabhi complete hoga jab:
  - [ ] `ScrollView` aur `FlatList` ka memory aur rendering difference clear ho.
  - [ ] `data`, `renderItem`, `keyExtractor` props ka purpose deeply samajh aaye.
  - [ ] `TodoItem.js` component ready ho aur `FlatList` smooth scroll ke saath dummy todos render kare.

Shuru karein:
1. Pehle `ScrollView` vs `FlatList` aur `FlatList` ke core props ka concept (What, Why, How + Android analogy) explain karein.
2. Phir mujhe step-by-step guide karein ki `TodoItem.js` kaise structure aur code karna hai, aur list kaise integrate karni hai.
```

---

## Kaun sa Skill use karna hai?

Block 4 ke liye [Skills.md](file:///Users/kshitizagnihotri/Project/TaskMatrix/Skills.md) ke hisaab se:

| Skill | Category | Kyun use karein? |
|-------|----------|------------------|
| **`frontend-ui-engineering`** | **Primary (Recommended)** | Block 4 list UI architecture, memory-efficient virtualized lists (`FlatList`), component decomposition (`TodoItem.js`), aur empty state handling par focused hai. |
| **`performance-optimization`** | **Supporting (Concept angle)** | `FlatList` ke windowing mechanism, `initialNumToRender`, `maxToRenderPerBatch`, aur memory management ke nuances samajhne ke liye. |
| **`context-engineering`** | **Alternative / Session Init** | Project background, rules aur paths load karne ke liye. |
