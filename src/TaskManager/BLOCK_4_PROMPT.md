# 🚀 Block 4 Prompt: Path Parameters vs Query Parameters (Advanced Read Routes)

> **How to use**: Naye chat session mein niche diye gaye prompt ko copy-paste karein.

---

### Copy-Paste Prompt for New Chat:

```markdown
/context-engineering /api-and-interface-design /source-driven-development

Main Python FastAPI scratch se seekh raha hun aur hamara roadmap `PLAN.md` mein defined hai.
Humaare **"Block 0"**, **"Block 1"**, **"Block 2"**, aur **"Block 3: Pydantic Validation & POST Route"** successfully complete ho chuke hain (`models.py`, `database.py`, aur `main.py` mein POST `/tasks` working state mein hain).

Is session mein hume **"Block 4: Path Parameters vs Query Parameters"** complete karna hai.

### 📌 Current Project State:
- Directory: `/Users/kshitizagnihotri/Project/TaskManager/TaskManagerApp`
- Virtualenv: `TaskManagerApp/venv` (Activated)
- Current Files: 
  - `models.py` (`TaskBase`, `TaskCreate`, `TaskResponse`)
  - `database.py` (`TASKS_DB` list)
  - `main.py` (`GET /`, `GET /tasks`, `POST /tasks`)
- Reference Roadmap: `../PLAN.md`
- Skills reference: `../Skills.md`

### 🎯 Block 4 Learning Objectives:
1. **Core Distinction: Path vs Query Parameters**:
   - REST API design rule: Kab URL mein **Path Parameter** use karna hai aur kab **Query Parameter**?
   - Resource Identity (Single Item) vs Resource Filtering/Sorting/Pagination (Collection).
2. **Path Parameters (`@app.get("/tasks/{task_id}")`)**:
   - URL path se dynamic variable `{task_id}` capture karna.
   - Automatic Type Casting & Validation: URL hamesha string hota hai, lekin FastAPI ise `int` me parse kaise karta hai aur agar koi `/tasks/abc` pass kare toh bina code likhe `422 Unprocessable Entity` kyun aata hai?
   - `TASKS_DB` me se specific ID ka task search karna.
3. **Query Parameters (`@app.get("/tasks")` enhancement)**:
   - FastAPI function parameters ko bina route string me likhe Query parameter kaise samajhta hai?
   - Filtering: `completed: Optional[bool] = None` query filter lagana. FastAPI `"true"`, `"1"`, `"false"` ko python boolean me kaise convert karta hai?
   - Optional Limit/Pagination: `limit: Optional[int] = None`.
4. **Validation with `Path` & `Query` helpers**:
   - `from fastapi import Path, Query` ka use karke boundary rules lagana (e.g. `task_id: int = Path(..., gt=0)` taaki negative IDs reject ho jayein).
5. **Interactive Testing**:
   - Swagger UI (`/docs`) par dono parameters ka automatic documentation aur testing dekhna.

### 👨‍🏫 Agent ke liye Strict Instructions (Mentor Role):
1. **Agent action nahi lenge**: Aap khud se files edit nahi karenge aur na hi commands run karenge jab tak main na bolun. Aap mujhe guide karenge, concept explain karenge, aur code main khud likhunga.
2. **Lego Building Block Framework (What, Why, How)**:
   - **What**: Path parameter aur Query parameter kya hain?
   - **Why**: REST architecture mein dono ka alag-alag role kyun hai?
   - **How**: Step-by-step code likhna (`main.py` update karna) aur Swagger UI par test karna.
3. **Pacing**: Pehle Path Parameter implement aur test karein, uske baad Query Parameter filter par move karein.

Aap mujhe mentor ke taur par guide karna shuru karein Block 4 ke 'What & Why' se!
```
