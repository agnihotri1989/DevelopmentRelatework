# Block 5 Prompt — State Management (useState & useEffect Deep Dive, Custom Hooks)

Ye prompt naye chat session mein copy-paste karein. Ye Block 5 ko start karega.

---

## Prompt (Copy karo 👇)

```
/api-and-interface-design

Main React Native project "TaskMatrix" (Smart Todo App with Local Analytics) build kar raha hun.
Mera background Android development (Kotlin/Java, Jetpack Compose, Architecture components) mein hai. Maine Block 0 se lekar Block 4 (UI layout, Flexbox, TextInput, TodoInput, FlatList, TodoItem) successfully complete kar liye hain.

📋 Complete Plan: /Users/kshitizagnihotri/Project/TaskMatrix/PLAN.md
📋 Skills reference: /Users/kshitizagnihotri/Project/TaskMatrix/Skills.md

---

## Aaj ka Goal: Block 5 — State Management & Business Logic (useState, useEffect, Custom Hook)

Ab tak hamare components static dummy data ya local form state use kar rahe the. Block 5 mein hum proper architectural separation of concerns implement karenge — UI se business logic ko alag karenge:

1. **Advanced `useState` with Arrays/Objects (Immutability):**
   - Direct mutation kyu banned hai (`todos.push()` vs `[...todos, newTodo]`).
   - Adding item: Spread operator `[newTodo, ...prevTodos]`.
   - Deleting item: `prevTodos.filter(todo => todo.id !== id)`.
   - Updating/Toggling item: `prevTodos.map(todo => todo.id === id ? { ...todo, completed: !todo.completed } : todo)`.
   - Android comparison: Kotlin data class `.copy()`, Kotlin `List` vs `MutableList`, StateFlow emitting new copies.
2. **`useEffect` Hook Fundamentals:**
   - What is a side effect? Why not call async/fetch directly in component body?
   - Dependency Array:
     - `[]` (empty) -> Run once on mount (Android `onCreate()` / Compose `LaunchedEffect(Unit)`).
     - `[todos]` -> Run jab `todos` change ho (Android `Observer` / Compose `LaunchedEffect(todos)`).
     - No dependency array -> Run on every render (avoid/danger zone).
   - Cleanup function (unmount / Android `onDestroy()`).
3. **Custom Hook Pattern (`useTodos.js`):**
   - Business logic aur state ko UI component se decouple karna.
   - Android Architecture comparison:
     - Custom Hook (`useTodos.js`) = Android `ViewModel`.
     - Returned state & methods = `StateFlow` values + ViewModel action functions (`addTodo()`, `deleteTodo()`, `toggleTodo()`).
4. **Hands-on Building:**
   - `src/hooks/useTodos.js` create karna with:
     - `todos` state
     - `selectedCategory` state (All, Work, Personal, Health)
     - `addTodo(title, category)`
     - `toggleTodo(id)`
     - `deleteTodo(id)`
     - `filterByCategory(category)`
   - `App.js` ya `HomeScreen.js` mein hook integrate karna aur end-to-end add/toggle/delete action test karna.

---

## Mentorship & Rules:
- **Lego approach:** Step-by-step building. Pehle immutable state update mechanics samajhna, phir hook structure, phir UI integration.
- **What, Why, How:** Har concept ke liye clear structure.
- **Android/Kotlin Analogies:** Hook ko `ViewModel` aur State immutability ko Kotlin `copy()`/`StateFlow` se link karke samjhana.
- **Mentor Mode (Strict):** Agent sirf guide karega, syntax aur patterns samjhayega, aur verification checklist batayega. Agent code direct write nahi karega jab tak main explicit allow na karun. Code main khud type karunga.
- **Checkpoint Verification:** Block 5 tabhi complete hoga jab:
  - [ ] Immutable operations (`map`, `filter`, spread) fluently samajh aa rahe hon.
  - [ ] `useEffect` dependency array ka rule aur mount lifecycle clear ho.
  - [ ] `useTodos.js` custom hook clean contract expose kare aur App mein new todo add, toggle, delete perfectly re-render kare bina state lose ya mutate kiye.

Shuru karein:
1. Pehle immutable state updates aur `useEffect` ka concept (What, Why, How + Android ViewModel/StateFlow analogy) explain karein.
2. Phir mujhe step-by-step guide karein ki `useTodos.js` custom hook kaise craft karna hai aur use HomeScreen/App mein kaise connect karna hai.
```

---

## Kaun sa Skill use karna hai?

Block 5 ke liye [Skills.md](file:///Users/kshitizagnihotri/Project/TaskMatrix/Skills.md) ke hisaab se:

| Skill | Category | Kyun use karein? |
|-------|----------|------------------|
| **`api-and-interface-design`** | **Primary (Recommended)** | Block 5 architecture aur contract boundary par focused hai: UI layers (`HomeScreen`) aur State layer (`useTodos`) ke beech clean public interface/API define karna, error semantics, aur state contract banana. |
| **`frontend-ui-engineering`** | **Supporting** | State management, component re-renders, aur React lifecycle hooks (`useState`, `useEffect`) ko correctly handle karne ke liye. |
| **`test-driven-development`** | **Supporting (Optional)** | Agar custom hook ke actions (add, toggle, delete) ko logic level par verify karna chahein. |
