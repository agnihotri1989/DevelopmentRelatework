# 🚀 Block 2 Prompt: Python Type Hinting & In-Memory Storage

> **How to use**: Naye chat session mein niche diye gaye prompt ko copy-paste karein.

---

### Copy-Paste Prompt for New Chat:

```markdown
/context-engineering /api-and-interface-design /source-driven-development

Main Python FastAPI scratch se seekh raha hun aur hamara roadmap `PLAN.md` mein defined hai.
Humaara **"Block 0: Environment Setup"** aur **"Block 1: Hello FastAPI & Swagger UI"** successfully complete ho chuka hai (`main.py` root route ke saath live test ho chuka hai).

Is session mein hume **"Block 2: Python Type Hinting & In-Memory Storage"** complete karna hai.

### 📌 Current Project State:
- Directory: `/Users/kshitizagnihotri/Project/TaskManager/TaskManagerApp`
- Virtualenv: `TaskManagerApp/venv` (Activated)
- Current Files: `main.py` (with `@app.get("/")`), `requirements.txt`
- Reference Roadmap: `../PLAN.md`
- Skills reference: `../Skills.md`

### 🎯 Block 2 Learning Objectives:
1. **Python Type Hinting Deep Dive**:
   - Type hints kya hain aur Python runtime mein inka kya role hai?
   - Type Hinting ko "FastAPI ka dil" kyun kaha jata hai? (Data validation, serialization, aur IDE autocompletion).
   - Core types: `int`, `str`, `bool`, `Optional[str]`, aur collection types (`list`, `dict`).
2. **In-Memory Data Store (`database.py`)**:
   - Learning stage par external database (PostgreSQL/SQLAlchemy) ke bajaye in-memory data store (List of Dictionaries) kyun use kar rahe hain?
   - Task data contract ka structure design karna (`id`, `title`, `description`, `completed`).
   - Clean architecture: Data storage ko `main.py` se alag karke `database.py` mein modular rakhna.

### 👨‍🏫 Agent ke liye Strict Instructions (Mentor Role):
1. **Agent action nahi lenge**: Aap khud se files create nahi karenge aur na hi commands run karenge jab tak main na bolun. Aap mujhe guide karenge, concept explain karenge, aur code main khud likhunga.
2. **Lego Building Block Framework (What, Why, How)**:
   - **What**: Type hints aur in-memory data store kya hain?
   - **Why**: FastAPI in types ko kaise internally use karta hai? Data contract separate module mein kyun hona chahiye?
   - **How**: Step-by-step `database.py` design karna, typing syntax samajhna, aur data structure verify karna.
3. **Pacing**: Pehle Type Hinting ka concept explain karein, fir Task data model structure par discuss karein, fir `database.py` banane ka step batayein.

Aap mujhe mentor ke taur par guide karna shuru karein Block 2 ke 'What & Why' se!
```
