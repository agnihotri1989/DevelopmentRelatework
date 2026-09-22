# Block 10 Prompt — Safe Areas, Edge-to-Edge & Final App Polish (The Graduation Block 🎓)

Ye prompt naye chat session mein copy-paste karein. Ye hamare learning roadmap ka aakhri block (**Block 10**) shuru karega.

---

## Prompt (Copy karo 👇)

```
/frontend-ui-engineering

Main React Native project "TaskMatrix" (Smart Todo App with Local Analytics) build kar raha hun.
Mera background Android development (Kotlin/Java, WindowInsetsCompat, fitsSystemWindows) mein hai. Maine Block 0 se lekar Block 9 successfully complete kar liye hain, aur meri app Android Emulator aur iOS Simulator dono par successfully run kar rahi hai.

📋 Complete Plan: /Users/kshitizagnihotri/Project/TaskMatrix/PLAN.md
📋 Skills reference: /Users/kshitizagnihotri/Project/TaskMatrix/Skills.md

---

## Aaj ka Goal: Block 10 — Safe Areas, System Insets & Production Polish (Graduation Block 🎓)

Ye hamari app ka final Lego block hai jismein hum UI ko notch, camera punch-holes, dynamic islands, aur navigation gesture bars ke mutabiq professional look denge:

1. **Safe Area & Window Insets Architecture:**
   - Problem: Notch, punch hole camera, rounded screen corners, aur iOS home indicator / Android gesture bar ke peeche content chup jana ya overlap hona.
   - Built-in `SafeAreaView` (from 'react-native') vs `react-native-safe-area-context` (Recommended):
     - Built-in sirf basic iOS support karta hai, dynamic insets aur Android support nahi karta.
     - `SafeAreaProvider` + `SafeAreaView` / `useSafeAreaInsets()` hook: Pure cross-platform solution.
   - Android comparison:
     - `SafeAreaView` = Android `android:fitsSystemWindows="true"`
     - `useSafeAreaInsets()` = Android `WindowInsetsCompat` / Compose `WindowInsets.safeDrawing`.
2. **StatusBar Styling & Control:**
   - `expo-status-bar` / React Native `StatusBar`:
     - Light/Dark theme content mode (`style="dark"` ya `"light"`).
     - Android translucent / immersive status bar handling.
3. **App-wide Polish & Edge-to-Edge Experience:**
   - `HomeScreen.js` aur `AnalyticsScreen.js` ko wrap karna using `SafeAreaView` with selective edges (`edges={['top', 'left', 'right']}`).
   - Tab Bar bottom padding check (ensure karna ki iOS home indicator bar tab icons ko cut na kare).
   - Keyboard handling polish: `KeyboardAvoidingView` test karna jab user todo type kar raha ho.
4. **Final Success Criteria Verification (Multi-Device):**
   - Android Emulator (with punch-hole/camera cutout) par check karna.
   - iOS Simulator (iPhone with Dynamic Island / Notch) par check karna.
   - 11 Lego Blocks ki complete checklist review karna:
     - [ ] JSX & Functional Components (Block 1)
     - [ ] StyleSheet & Flexbox (Block 2)
     - [ ] TextInput & TouchableOpacity (Block 3)
     - [ ] FlatList & TodoItem (Block 4)
     - [ ] useState, useEffect, useTodos (Block 5)
     - [ ] AsyncStorage persistence (Block 6)
     - [ ] React Navigation Bottom Tabs (Block 7)
     - [ ] useMemo Smart Analytics (Block 8)
     - [ ] Platform.select & Shadows (Block 9)
     - [ ] SafeAreaView & Notch handling (Block 10)

---

## Mentorship & Rules:
- **Lego approach:** Step-by-step building. Pehle Safe Area Insets aur WindowInsets ka mental model samajhna, phir screens aur navigator ko wrap karna, phir final UI audit karna.
- **What, Why, How:** Har concept ke liye clear breakdown.
- **Android/Kotlin Analogies:** Safe Area ko `WindowInsetsCompat` aur `fitsSystemWindows` se link karke samjhana.
- **Mentor Mode (Strict):** Agent sirf guide karega, syntax explain karega, aur emulator test inspection points batayega. Agent code direct write nahi karega jab tak main allow na karun. Code main khud type karunga.
- **Checkpoint Verification:** Block 10 tabhi complete hoga jab:
  - [ ] Android aur iOS dono par header notch/punch-hole ke niche cut na ho.
  - [ ] Bottom tab bar gesture bar ke upar safely positioned ho.
  - [ ] Pure TaskMatrix project ka end-to-end user flow seamless run kare.

Shuru karein:
1. Pehle Safe Area, `SafeAreaProvider`, aur `useSafeAreaInsets` ka concept (What, Why, How + Android WindowInsetsCompat analogy) explain karein.
2. Phir mujhe step-by-step guide karein ki hamare screens aur navigation mein SafeAreaView kaise integrate aur polish karna hai.
```

---

## Kaun sa Skill use karna hai?

Block 10 ke liye [Skills.md](file:///Users/kshitizagnihotri/Project/TaskMatrix/Skills.md) ke hisaab se:

| Skill | Category | Kyun use karein? |
|-------|----------|------------------|
| **`frontend-ui-engineering`** | **Primary (Recommended)** | Block 10 safe areas, responsive viewport insets (Notch/Dynamic Island), device system bars, and visual UI polish/edge-to-edge rendering par focused hai. |
| **`shipping-and-launch`** | **Supporting (Grand Finale)** | Kyunki ye final block hai, ye skill end-to-end pre-launch sanity checklist aur cross-device quality checks ke liye ideal context provide karta hai. |
| **`context-engineering`** | **Session Init** | Naye chat session ke clean setup ke liye. |
