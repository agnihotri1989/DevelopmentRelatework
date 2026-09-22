# Spec: TaskMatrix — Smart Todo App with Local Analytics

## Objective

**Kya bana rahe hain?** Ek smart todo app jismein local analytics dashboard bhi ho — React Native (Expo) mein.

**Kyun?** React Native ke core concepts seekhne ke liye ek real project ke through. Har concept ko ek "Lego block" ki tarah ek-ek karke build karenge. Goal hai **confident hona** React Native mein, not just a finished app.

**Kisne use karna hai?** Tum khud — ye ek learning project hai.

**User Stories:**
1. User todos add, complete, delete kar sake
2. Todos fixed categories (Work, Personal, Health) mein organize ho sakein
3. App band karne pe data save rahe (AsyncStorage)
4. Ek Analytics screen pe total todos, completion rate, category-wise breakdown dikhe
5. App Android pe sahi dikhe (SafeAreaView, Platform-specific code)

**MVP Scope:** Basic CRUD + Categories + Persistence + Simple Analytics
**Future Add-ons (baad mein):** Daily streak, Weekly chart

---

## Tech Stack

| Tool | Why? |
|------|------|
| **Expo** (managed workflow) | Easy setup, no Xcode/Android Studio build config needed, hot reload built-in |
| **JavaScript (ES6+)** | Beginner-friendly, TypeScript baad mein seekhenge |
| **AsyncStorage** (`@react-native-async-storage/async-storage`) | Local persistence (Android ka SharedPreferences jaisa) |
| **React Navigation** (`@react-navigation/native`) | Screen navigation (Android ka Fragment Navigation jaisa) |
| **Expo SDK** | SafeAreaView, StatusBar, etc. built-in milte hain |

> **Note:** No Redux, No TypeScript, No Backend — sirf React ke built-in hooks se kaam chalega. Focus concepts pe hai, libraries pe nahi.

---

## Commands

```bash
# Project create (one-time setup)
npx create-expo-app@latest TaskMatrix

# Development
npx expo start                  # Expo dev server start
# Phone pe: Expo Go app install karo, QR scan karo
# Android Emulator pe: terminal mein 'a' press karo

# Packages install (jab zaroorat hogi)
npx expo install @react-native-async-storage/async-storage
npx expo install @react-navigation/native @react-navigation/bottom-tabs
npx expo install react-native-screens react-native-safe-area-context
```

---

## Project Structure

```
TaskMatrix/
├── src/
│   ├── components/          → Reusable UI building blocks
│   │   ├── TodoItem.js      → Single todo card component
│   │   ├── TodoInput.js     → Text input + add button
│   │   ├── CategoryFilter.js → Category filter buttons
│   │   └── StatCard.js      → Analytics stat card
│   ├── screens/             → Full page screens
│   │   ├── HomeScreen.js    → Main todo list screen
│   │   └── AnalyticsScreen.js → Stats dashboard
│   ├── hooks/               → Custom React hooks
│   │   ├── useTodos.js      → Todo CRUD + state logic
│   │   └── useAnalytics.js  → Analytics calculations
│   ├── storage/             → Data persistence layer
│   │   └── asyncStorage.js  → AsyncStorage wrapper functions
│   ├── utils/               → Helper functions
│   │   ├── constants.js     → Categories, colors, keys
│   │   └── helpers.js       → Date formatting, ID generation
│   └── navigation/          → App navigation setup
│       └── AppNavigator.js  → Tab-based navigation
├── App.js                   → Root component
└── package.json
```

> **Android Analogy:** `screens/` = Activities/Fragments, `components/` = Custom Views/ViewHolders, `hooks/` = ViewModels, `storage/` = SharedPreferences wrapper, `navigation/` = NavGraph

---

## 🧱 Lego Blocks — Learning Roadmap (11 Blocks: Block 0 → Block 10)

| Block | Concept | Kya Banayenge |
|-------|---------|---------------|
| **Block 0** | JS/ES6 Essentials (Arrow Functions, Destructuring, Spread, Template Literals, Array Methods, Async/Await) | JavaScript foundation — koi file nahi, sirf practice |
| **Block 1** | JSX, Functional Components, View, Text | App.js — Hello TaskMatrix header |
| **Block 2** | StyleSheet.create, Flexbox, Dynamic Styling | Theme/color system, styled components |
| **Block 3** | TextInput, TouchableOpacity, useState (intro) | TodoInput.js component |
| **Block 4** | ScrollView vs FlatList, list rendering | TodoItem.js + HomeScreen FlatList |
| **Block 5** | useState (advanced), useEffect, custom hooks | useTodos.js — CRUD operations |
| **Block 6** | AsyncStorage, async/await in practice | storage/asyncStorage.js + persistence |
| **Block 7** | React Navigation, Bottom Tabs | AppNavigator.js — Home + Analytics tabs |
| **Block 8** | useMemo, computed/derived data | useAnalytics.js + AnalyticsScreen.js |
| **Block 9** | Platform.select, Platform.OS | Platform-specific UI tweaks |
| **Block 10** | SafeAreaView, notch handling, polish | Final safe area + polish |

---

## Block Details

### Block 0: JavaScript/ES6 Essentials — Pehle Foundation

**Topics:**
1. Arrow Functions → Kotlin lambdas jaisa
2. Template Literals → Kotlin string interpolation jaisa
3. Destructuring → Kotlin componentN() jaisa
4. Spread Operator (...) → Kotlin copy() jaisa
5. Array Methods (map, filter, find) → Same as Kotlin
6. Async/Await → Kotlin Coroutines jaisa

**Checkpoint:**
- [ ] Arrow function likh sakte ho?
- [ ] Template literal mein variable daal sakte ho?
- [ ] Object/Array destructuring kar sakte ho?
- [ ] Spread operator se naya array/object bana sakte ho?
- [ ] map, filter, find ka difference samajh aaya?
- [ ] async/await with try/catch likh sakte ho?

---

### Block 1: Hello TaskMatrix — JSX & Functional Components

**Concepts:** JSX Syntax, Functional Components, `View`, `Text`
**Android Analogy:** View → ViewGroup, Text → TextView, Component → @Composable fun
**Build:** App.js mein header with app title
**Checkpoint:** JSX `{}` expressions, View/Text nesting samajh aaye

---

### Block 2: Styling Mastery — StyleSheet.create & Dynamic Styling

**Concepts:** StyleSheet.create, Flexbox, Conditional Styles
**Android Analogy:** StyleSheet → styles.xml, Flexbox → LinearLayout + ConstraintLayout
**Build:** Theme system, styled header, StatCard component
**Checkpoint:** flexDirection, justifyContent, alignItems, style arrays

---

### Block 3: User Input — TextInput & TouchableOpacity

**Concepts:** TextInput, TouchableOpacity, useState (intro)
**Android Analogy:** TextInput → EditText, TouchableOpacity → Button, useState → MutableLiveData
**Build:** TodoInput.js component
**Checkpoint:** [value, setValue] pattern, controlled input

---

### Block 4: Lists Done Right — ScrollView vs FlatList

**Concepts:** ScrollView, FlatList, renderItem, keyExtractor
**Android Analogy:** ScrollView → ScrollView, FlatList → RecyclerView
**Build:** TodoItem.js + HomeScreen FlatList
**Checkpoint:** data, renderItem, keyExtractor, ScrollView vs FlatList difference

---

### Block 5: State Management — useState & useEffect Deep Dive

**Concepts:** useState with arrays/objects, useEffect, custom hooks
**Android Analogy:** useEffect → onCreate/LaunchedEffect, Custom Hook → ViewModel
**Build:** useTodos.js custom hook (add, delete, toggle, filter)
**Checkpoint:** Immutable updates, useEffect dependency array

---

### Block 6: Data Persistence — AsyncStorage

**Concepts:** AsyncStorage, JSON.stringify/parse, auto-save
**Android Analogy:** AsyncStorage → SharedPreferences
**Build:** storage/asyncStorage.js + persistence in useTodos
**Checkpoint:** Practical async/await, auto-save on state change

---

### Block 7: Navigation — Multiple Screens

**Concepts:** React Navigation, Bottom Tab Navigator
**Android Analogy:** Tab Navigator → BottomNavigationView + NavGraph
**Build:** AppNavigator.js — Home + Analytics tabs
**Checkpoint:** Navigation container, screen registration, tab icons

---

### Block 8: Smart Analytics — useMemo

**Concepts:** useMemo, derived/computed data
**Android Analogy:** useMemo → derivedStateOf / Transformations.map()
**Build:** useAnalytics.js + AnalyticsScreen.js with stat cards
**Checkpoint:** useMemo usage, dependency array role

---

### Block 9: Platform-Specific Code — Platform.select

**Concepts:** Platform.select, Platform.OS
**Android Analogy:** Platform.select → Build.VERSION.SDK_INT checks
**Build:** Platform-specific shadows, typography tweaks
**Checkpoint:** Platform.select pattern, platform-specific files

---

### Block 10: Safe Areas & Polish — SafeAreaView

**Concepts:** SafeAreaView, notch handling
**Android Analogy:** SafeAreaView → WindowInsetsCompat / fitsSystemWindows
**Build:** SafeAreaView integration + final polish
**Checkpoint:** Safe area insets, multi-device testing

---

## Code Style

- Components: `PascalCase` (TodoItem, StatCard)
- Files: `PascalCase.js` for components, `camelCase.js` for hooks/utils
- Hooks: `use` prefix (useTodos, useAnalytics)
- Constants: `UPPER_SNAKE_CASE` (STORAGE_KEY, CATEGORIES)
- Styles: `camelCase` (completedContainer, deleteButton)
- Always use `StyleSheet.create`, never inline styles
- Always use immutable state updates

---

## Boundaries

### Always:
- Pehle concept samjho (What/Why), phir code karo (How)
- State immutably update karo
- StyleSheet.create use karo
- Har Block ke baad app run karke dekho
- `npx expo install` use karo packages ke liye

### Ask First:
- Naya package install karne se pehle
- Concept samajh nahi aaya toh poocho
- Error 10 min mein solve na ho toh poocho

### Never:
- Copy-paste without understanding
- Class components (sirf functional)
- Redux/MobX (hooks se kaam chalao)
- TypeScript (pehle JS mein confident ho jao)
- Ek saath saare blocks implement karna

---

## Mentorship Rules

**Agent sirf GUIDE karega, ACTION nahi lega jab tak student nahi bolega.**

1. Har block ke shuru mein: concept explain (What, Why, How + Android Analogy)
2. Code student likhega — agent batayega kya likhna hai
3. Stuck ho toh: hints pehle, direct answer baad mein
4. Block complete → checkpoint verify
5. Pace student ki — koi rush nahi

---

## Success Criteria

| # | Criteria |
|---|----------|
| 1 | App start pe saved todos dikhen (AsyncStorage se load) |
| 2 | Todo add, complete, delete ho sake |
| 3 | Categories se filter ho sake (Work/Personal/Health) |
| 4 | Analytics: total, completion %, category breakdown |
| 5 | SafeAreaView: content notch ke neeche na jaaye |
| 6 | Saare 11 Lego Blocks complete |
| 7 | Har concept confidently explain kar sako |
