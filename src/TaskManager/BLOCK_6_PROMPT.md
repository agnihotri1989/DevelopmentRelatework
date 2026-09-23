# 🚀 Block 6 Prompt: Custom HTTP Exceptions & Global Error Handling

> **How to use**: Naye chat session mein niche diye gaye prompt ko copy-paste karein.

---

### Copy-Paste Prompt for New Chat:

```markdown
/context-engineering /api-and-interface-design /source-driven-development /debugging-and-error-recovery

Main Python FastAPI scratch se seekh raha hun aur hamara roadmap `PLAN.md` mein defined hai.
Humaare **"Block 0"** se lekar **"Block 5: Write Routes (PUT & DELETE)"** successfully complete ho chuke hain (Full CRUD `main.py` mein live hai aur `test_main.py` mein automated tests bhi configured hain).

Is session mein hume **"Block 6: Custom HTTP Exceptions & Global Error Handling"** complete karna hai.

### 📌 Current Project State:
- Directory: `/Users/kshitizagnihotri/Project/TaskManager/TaskManagerApp`
- Virtualenv: `TaskManagerApp/venv` (Activated)
- Current Files:
  - `models.py` (`TaskBase`, `TaskCreate`, `TaskResponse`, `TaskUpdate`)
  - `database.py` (`TASKS_DB` in-memory list)
  - `main.py` (Full CRUD endpoints: `GET /`, `GET /tasks`, `GET /tasks/{id}`, `POST /tasks`, `PUT /tasks/{id}`, `DELETE /tasks/{id}`)
  - `test_main.py` (Pytest test suite)
- Reference Roadmap: `../PLAN.md`
- Skills reference: `../Skills.md`

### 🎯 Block 6 Learning Objectives:
1. **API Error Semantics & Why Custom Exceptions?**:
   - Default FastAPI `HTTPException` sirf `{"detail": "..."}` return karta hai. Production APIs mein consistent, structured error envelope (jaise `error_code`, `message`, `status_code`) kyun zaroori hota hai?
   - Domain-driven / Business Logic errors (jaise duplicate task title rokna — `400 Bad Request`).
2. **Custom Python Domain Exceptions**:
   - Custom Python exception classes create karna (e.g. `class TaskNotFoundException(Exception)` aur `class DuplicateTaskException(Exception)`).
   - Route handlers mein directly `HTTPException` raise karne ke bajaye clean domain exceptions raise karne ka architectural benefit.
3. **FastAPI Global Exception Handlers (`@app.exception_handler`)**:
   - `@app.exception_handler(TaskNotFoundException)` aur `JSONResponse` ka use karke custom exception ko clean HTTP response mein convert karna.
   - Pydantic validation errors (422) ya default HTTP errors ko capture aur format karne ka tareeqa.
4. **Verification**:
   - Swagger UI (`/docs`) aur `test_main.py` ke through verify karna ki standard error responses aur status codes accurately return ho rahe hain.

### 👨‍🏫 Agent ke liye Strict Instructions (Mentor Role):
1. **Agent action nahi lenge**: Aap khud se files edit nahi karenge aur na hi commands run karenge jab tak main na bolun. Aap mujhe guide karenge, concept explain karenge, aur code main khud likhunga.
2. **Lego Building Block Framework (What, Why, How)**:
   - **What**: Custom exceptions aur Global exception handlers kya hote hain?
   - **Why**: Error contracts kyun zaroori hain aur software architecture ko clean kaise banate hain?
   - **How**: Step 1: Custom exception classes design karna, Step 2: `@app.exception_handler` register karna, Step 3: Routes update karna, Step 4: Verification.
3. **Pacing**: Ek saath sab code na dein. Pehle concept aur architecture explain karein, fir step-by-step implementation karwayen.

Aap mujhe mentor ke taur par guide karna shuru karein Block 6 ke 'What & Why' se!
```
