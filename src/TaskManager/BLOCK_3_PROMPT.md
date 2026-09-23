# 🚀 Block 3 Prompt: Data Validation with Pydantic Schemas

> **How to use**: Naye chat session mein niche diye gaye prompt ko copy-paste karein.

---

### Copy-Paste Prompt for New Chat:

```markdown
/context-engineering /api-and-interface-design /security-and-hardening /source-driven-development

Main Python FastAPI scratch se seekh raha hun aur hamara roadmap `PLAN.md` mein defined hai.
Humaare **"Block 0: Setup"**, **"Block 1: Hello FastAPI & Swagger"**, aur **"Block 2: Type Hints & In-Memory Store"** successfully complete ho chuke hain (`database.py` mein `TASKS_DB` ready hai aur `main.py` mein `/tasks` list return kar raha hai).

Is session mein hume **"Block 3: Data Validation & Serialization with Pydantic Models"** complete karna hai.

### 📌 Current Project State:
- Directory: `/Users/kshitizagnihotri/Project/TaskManager/TaskManagerApp`
- Virtualenv: `TaskManagerApp/venv` (Activated)
- Current Files: `main.py`, `database.py` (with `TASKS_DB`), `requirements.txt`
- Reference Roadmap: `../PLAN.md`
- Skills reference: `../Skills.md`

### 🎯 Block 3 Learning Objectives:
1. **The "Why Pydantic?" Revelation**:
   - Python standard `dict` vs Pydantic `BaseModel` mein kya antar hai?
   - Kyun raw dictionary mein koi bhi galat data (e.g. invalid type ya missing keys) daal sakta hai aur Pydantic is boundary ko runtime par kaise strictly protect karta hai?
2. **Contract-First Design (`models.py`)**:
   - Pydantic V2 ke idiomatic models create karna:
     - `TaskBase`: Common fields (`title`, `description`, `completed`).
     - `TaskCreate`: Jo user task create karte waqt bhejega (bina `id` ke).
     - `TaskResponse`: Jo API client ko return karegi (with `id`).
   - Field validation using `Field(..., min_length=..., max_length=...)` for boundary defense.
3. **Pydantic in Action**:
   - Request Body validation aur Automatic `422 Unprocessable Entity` error behavior ko samajhna.
   - Swagger UI (`/docs`) mein Pydantic models automatically request/response schema docs kaise generate karte hain dekhna.

### 👨‍🏫 Agent ke liye Strict Instructions (Mentor Role):
1. **Agent action nahi lenge**: Aap khud se files create nahi karenge aur na hi commands run karenge jab tak main na bolun. Aap mujhe guide karenge, concept explain karenge, aur code main khud likhunga.
2. **Lego Building Block Framework (What, Why, How)**:
   - **What**: Pydantic BaseModel, Request Body, Response Schema kya hain?
   - **Why**: Separation of schemas kyun zaroori hai? (Kyun user se `id` nahi mangna chahiye creation par?)
   - **How**: `models.py` create karna, Pydantic V2 syntax likhna, aur `/docs` par schema verify karna.
3. **Pacing**: Pehle "Why Pydantic over dict" samjhayen, fir `models.py` ke structure par discuss karein, fir implementation aur verification.

Aap mujhe mentor ke taur par guide karna shuru karein Block 3 ke 'What & Why' se!
```
