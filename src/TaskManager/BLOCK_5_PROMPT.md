# 🚀 Block 5 Prompt: Write Routes (PUT & DELETE) and HTTP Status Codes

> **How to use**: Naye chat session mein niche diye gaye prompt ko copy-paste karein.

---

### Copy-Paste Prompt for New Chat:

```markdown
/context-engineering /api-and-interface-design /incremental-implementation /source-driven-development

Main Python FastAPI scratch se seekh raha hun aur hamara roadmap `PLAN.md` mein defined hai.
Humaare **"Block 0"**, **"Block 1"**, **"Block 2"**, **"Block 3"**, aur **"Block 4: Path & Query Parameters"** successfully complete ho chuke hain (`main.py` mein `GET /`, `GET /tasks` with filters, `GET /tasks/{task_id}`, aur `POST /tasks` working state mein hain).

Is session mein hume **"Block 5: Write Routes (PUT & DELETE), Status Codes & Completing CRUD"** complete karna hai.

### 📌 Current Project State:
- Directory: `/Users/kshitizagnihotri/Project/TaskManager/TaskManagerApp`
- Virtualenv: `TaskManagerApp/venv` (Activated)
- Current Files:
  - `models.py` (`TaskBase`, `TaskCreate`, `TaskResponse`)
  - `database.py` (`TASKS_DB` list)
  - `main.py` (`GET /`, `GET /tasks`, `GET /tasks/{task_id}`, `POST /tasks`)
- Reference Roadmap: `../PLAN.md`
- Skills reference: `../Skills.md`

### 🎯 Block 5 Learning Objectives:
1. **Designing Update Schema (`TaskUpdate` in `models.py`)**:
   - `TaskCreate` vs `TaskUpdate` mein kya farak hai?
   - Update karte waqt fields (`title`, `description`, `completed`) optional kyun hone chahiye?
   - Pydantic V2 ka `model_dump(exclude_unset=True)` kya karta hai aur partial update ke liye yeh kyun zaroori hai?
2. **Update Route (`@app.put("/tasks/{task_id}")`)**:
   - REST semantics mein `PUT` ka meaning aur Idempotency ka concept.
   - Task search karna: Agar `task_id` na mile toh clean `404 Not Found` raise karna.
   - Existing dictionary fields update karke updated `TaskResponse` return karna.
3. **Delete Route (`@app.delete("/tasks/{task_id}")`)**:
   - Status Code `204 No Content` kya hota hai aur HTTP standard ke mutabik 204 response mein koi response body kyun nahi honi chahiye?
   - `TASKS_DB` se task remove karna aur agar na mile toh `404 Not Found` dena.
4. **Standard HTTP Status Codes Mastery**:
   - `from fastapi import status` module ka standard use (`status.HTTP_200_OK`, `status.HTTP_201_CREATED`, `status.HTTP_204_NO_CONTENT`, `status.HTTP_404_NOT_FOUND`).
5. **Full CRUD Verification**:
   - Swagger UI (`/docs`) par poori lifecycle test karna: **Create (POST)** ➔ **Read (GET)** ➔ **Update (PUT)** ➔ **Delete (DELETE)** ➔ **Verify Deleted (GET 404)**.

### 👨‍🏫 Agent ke liye Strict Instructions (Mentor Role):
1. **Agent action nahi lenge**: Aap khud se files edit nahi karenge aur na hi commands run karenge jab tak main na bolun. Aap mujhe guide karenge, concept explain karenge, aur code main khud likhunga.
2. **Lego Building Block Framework (What, Why, How)**:
   - **What**: PUT, DELETE, 204 No Content, aur partial updates kya hain?
   - **Why**: REST architecture mein status codes aur method semantics ka standard follow karna kyun crucial hai?
   - **How**: Step 1: `models.py` mein `TaskUpdate` model, Step 2: `PUT` route, Step 3: `DELETE` route, Step 4: Swagger UI par interactive verification.
3. **Pacing**: Ek saath sab code na dein. Pehle `TaskUpdate` model par discuss karein, fir `PUT`, fir `DELETE`.

Aap mujhe mentor ke taur par guide karna shuru karein Block 5 ke 'What & Why' se!
```
