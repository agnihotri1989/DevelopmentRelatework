# Block 9 Prompt — Platform-Specific Code (Platform.select, Platform.OS & Shadows)

Ye prompt naye chat session mein copy-paste karein. Ye Block 9 ko start karega.

---

## Prompt (Copy karo 👇)

```
/frontend-ui-engineering

Main React Native project "TaskMatrix" (Smart Todo App with Local Analytics) build kar raha hun.
Mera background Android development (Kotlin/Java, Android SDK/Resource Qualifiers) mein hai. Maine Block 0 se lekar Block 8 (UI, Flexbox, FlatList, useTodos, AsyncStorage, React Navigation, useMemo analytics) successfully complete kar liye hain.

⚠️ Environment Note: Mere paas physical phone nahi hai, main test karne ke liye **Android Emulator** aur **iOS Simulator** (Mac par) use karunga.

📋 Complete Plan: /Users/kshitizagnihotri/Project/TaskMatrix/PLAN.md
📋 Skills reference: /Users/kshitizagnihotri/Project/TaskMatrix/Skills.md

---

## Aaj ka Goal: Block 9 — Platform-Specific Code (`Platform.select` & `Platform.OS`)

React Native ek single codebase provide karta hai, lekin Android aur iOS ke native rendering engine, design guidelines (Material vs Cupertino), aur styling support alag hote hain. Block 9 mein hum platform adaptability deeply seekhenge:

1. **`Platform` Module Fundamentals:**
   - `Platform.OS`: Returns `'android'` ya `'ios'` (if/else conditional logic).
   - `Platform.Version`: Android API level (e.g. 33) ya iOS version string (e.g. "17.0").
   - `Platform.select()`: Clean object mapping pattern:
     ```javascript
     const containerStyle = Platform.select({
       ios: { shadowColor: '#000', ... },
       android: { elevation: 4 },
       default: { ... }
     });
     ```
   - Platform-specific file extensions: `Component.android.js` vs `Component.ios.js` (Metro bundler compile time par select karta hai).
   - Android comparison:
     - `Platform.select` = Android resource qualifiers (`res/values/`, `res/values-v21/`) ya runtime `Build.VERSION.SDK_INT` check.
2. **Key Platform Differences jo hum tackle karenge:**
   - **Elevation vs Box Shadow:**
     - Android: Sirf `elevation: number` support karta hai (RenderNode elevation / native drop shadow).
     - iOS: 4 properties require karta hai (`shadowColor`, `shadowOffset`, `shadowOpacity`, `shadowRadius`).
   - **Typography & Fonts:**
     - Android default system font: `Roboto` / sans-serif.
     - iOS default system font: `System` / San Francisco (`-apple-system`).
   - **Status Bar & Header Spacing:**
     - Android: Translucent / immersive status bar handling.
     - iOS: Dynamic island / notch padding considerations.
3. **Hands-on Building & Refactoring:**
   - Universal shadow helper function / style utility banana (`src/utils/shadows.js` ya constants mein) jo platform detect karke appropriate shadow attributes inject kare.
   - Ye shadow `StatCard.js`, `TodoItem.js`, aur `TodoInput.js` cards par apply karna.
   - `Platform.select` se buttons aur font-weights ko dono platforms ke liye native feel dena.
4. **Simulator / Emulator Verification:**
   - Terminal mein `a` press karke Android Emulator par test karna (elevation check karna).
   - Terminal mein `i` press karke iOS Simulator par test karna (soft box-shadow check karna).
   - Verify karna ki koi warning ya crash nahi ho raha.

---

## Mentorship & Rules:
- **Lego approach:** Step-by-step building. Pehle `Platform.select` aur shadow differences ka concept samajhna, phir helper utility banana, phir components mein refactor karke dono emulators par check karna.
- **What, Why, How:** Har concept ke liye clear breakdown.
- **Android/Kotlin Analogies:** Platform check ko Android `Build.VERSION` aur resource qualifier directories se link karke samjhana.
- **Mentor Mode (Strict):** Agent sirf guide karega, syntax aur emulator verification tips batayega. Agent code direct write nahi karega jab tak main explicit allow na karun. Code main khud type karunga.
- **Checkpoint Verification:** Block 9 tabhi complete hoga jab:
  - [ ] `Platform.select` aur `Platform.OS` ka working syntax clear ho.
  - [ ] Android elevation aur iOS 4-part shadow ka difference deeply samajh aaye.
  - [ ] Cards par Android Emulator par native elevation shadow aur iOS Simulator par smooth blur shadow dikhai de.

Shuru karein:
1. Pehle `Platform.select`, `Platform.OS`, aur Android vs iOS shadow mechanics (What, Why, How + Android analogy) explain karein.
2. Phir mujhe step-by-step guide karein ki reusable shadow utility kaise banani hai aur use hamare components mein kaise apply karna hai.
```

---

## Kaun sa Skill use karna hai?

Block 9 ke liye [Skills.md](file:///Users/kshitizagnihotri/Project/TaskMatrix/Skills.md) ke hisaab se:

| Skill | Category | Kyun use karein? |
|-------|----------|------------------|
| **`frontend-ui-engineering`** | **Primary (Recommended)** | Block 9 cross-platform styling nuances (Android Material elevation vs iOS shadows, fonts, cross-OS design systems) aur responsive platform ergonomics par focused hai. |
| **`api-and-interface-design`** | **Supporting** | Platform-agnostic shadow helper API (`createShadow(elevation)`) design karne ke liye. |
| **`context-engineering`** | **Session Init** | Naye chat session ke initialization ke liye. |
