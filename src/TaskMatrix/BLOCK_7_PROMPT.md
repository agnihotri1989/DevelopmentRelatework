# Block 7 Prompt — Navigation (React Navigation & Bottom Tab Navigator)

Ye prompt naye chat session mein copy-paste karein. Ye Block 7 ko start karega.

---

## Prompt (Copy karo 👇)

```
/frontend-ui-engineering

Main React Native project "TaskMatrix" (Smart Todo App with Local Analytics) build kar raha hun.
Mera background Android development (Kotlin/Java, Jetpack Navigation Component, NavHost, BottomNavigationView) mein hai. Maine Block 0 se lekar Block 6 (UI components, Flexbox, FlatList, useTodos custom hook, AsyncStorage persistence) successfully complete kar liye hain.

📋 Complete Plan: /Users/kshitizagnihotri/Project/TaskMatrix/PLAN.md
📋 Skills reference: /Users/kshitizagnihotri/Project/TaskMatrix/Skills.md

---

## Aaj ka Goal: Block 7 — Multi-Screen Architecture (React Navigation & Bottom Tabs)

Ab tak hamari saari UI ek single screen (`App.js`) par render ho rahi thi. Block 7 mein hum multi-screen structure build karenge taaki user Todos aur Analytics ke beech seamlessly switch kar sake:

1. **React Navigation Architecture & Fundamentals:**
   - Navigation tree structure: `NavigationContainer` (App level context provider).
   - Navigator vs Screen pattern (`Tab.Navigator` and `Tab.Screen`).
   - Android comparison:
     - `NavigationContainer` = `NavHost` / `NavHostFragment`.
     - `createBottomTabNavigator` = `BottomNavigationView` + Android Navigation Graph (`nav_graph.xml`).
     - Screen Components = Android `Fragment` / Compose navigation composable destinations.
2. **Setup & Dependencies:**
   - Expo safe installation: `@react-navigation/native`, `@react-navigation/bottom-tabs`, `react-native-screens`, `react-native-safe-area-context`.
   - Vector icons setup (`@expo/vector-icons` built-in in Expo) for Tab Bar icons (e.g. checkmark-done for Todos, stats-chart for Analytics).
3. **Screen Decomposition:**
   - `src/screens/HomeScreen.js`: Exisiting Todo UI (Header, TodoInput, CategoryFilter, FlatList) ko clean full screen component banana.
   - `src/screens/AnalyticsScreen.js`: Placeholder screen banana (jise hum Block 8 mein useMemo ke sath full stats dashboard banayenge).
   - Global state sharing strategy: `useTodos` hook ko clean tarike se screens ke sath connect karna (prop drilling vs custom hook sharing).
4. **Hands-on Building (`src/navigation/AppNavigator.js`):**
   - Tab navigator create karna with active/inactive tab colors, styling, aur icons.
   - `App.js` ko wrap karna with `<NavigationContainer><AppNavigator /></NavigationContainer>`.
   - Verify smooth tab switching without losing state or crash.

---

## Mentorship & Rules:
- **Lego approach:** Step-by-step building. Pehle navigation container aur tab architecture samajhna, phir screens extract karna, phir navigation assemble karna.
- **What, Why, How:** Har concept ke liye clear breakdown.
- **Android/Kotlin Analogies:** NavigationContainer ko NavHost aur Tab.Screen ko Fragment/NavDestination se link karke samjhana.
- **Mentor Mode (Strict):** Agent sirf guide karega, syntax aur navigation options samjhayega, aur test steps batayega. Agent code direct write nahi karega jab tak main explicit allow na karun. Code main khud type karunga.
- **Checkpoint Verification:** Block 7 tabhi complete hoga jab:
  - [ ] React Navigation setup error-free install ho.
  - [ ] `HomeScreen.js` aur `AnalyticsScreen.js` standalone components ke roop mein exist karein.
  - [ ] Bottom tab bar smoothly screen switch kare with active indicator and icons.
  - [ ] Todos add karne ke baad Analytics tab pe jao aur wapas aao toh data intact rahe.

Shuru karein:
1. Pehle React Navigation aur Bottom Tabs ka concept (What, Why, How + Android NavHost/BottomNavigationView analogy) aur installation commands explain karein.
2. Phir mujhe step-by-step guide karein ki screens kaise extract karni hain aur `AppNavigator.js` kaise assemble karna hai.
```

---

## Kaun sa Skill use karna hai?

Block 7 ke liye [Skills.md](file:///Users/kshitizagnihotri/Project/TaskMatrix/Skills.md) ke hisaab se:

| Skill | Category | Kyun use karein? |
|-------|----------|------------------|
| **`frontend-ui-engineering`** | **Primary (Recommended)** | Block 7 application-level UI routing, bottom navigation tabs, screen lifecycle, styling of tab bars, aur icons orchestration par focused hai. |
| **`api-and-interface-design`** | **Supporting** | Screens ke beech data contract/parameters passing aur state flow boundaries maintain karne ke liye. |
| **`context-engineering`** | **Session Init** | Naye chat session mein project background aur files initialize karne ke liye. |
