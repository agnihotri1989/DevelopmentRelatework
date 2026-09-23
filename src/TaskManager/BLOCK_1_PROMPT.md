# 🚀 Block 1 Prompt: First FastAPI App, ASGI Server & Auto Documentation

> **How to use**: Naye chat session mein niche diye gaye prompt ko copy-paste karein.

---

### Copy-Paste Prompt for New Chat:

```markdown
/context-engineering /source-driven-development

Main Python FastAPI scratch se seekh raha hun aur hamara roadmap `PLAN.md` mein defined hai.
Humaara **"Block 0: Environment Setup"** successfully complete ho chuka hai (`TaskManagerApp/venv` ready hai aur dependencies installed hain).

Is session mein hume **"Block 1: Hello FastAPI, ASGI Server & Auto Documentation"** complete karna hai.

### 📌 Current Project State:
- Directory: `/Users/kshitizagnihotri/Project/TaskManager/TaskManagerApp`
- Virtualenv: `TaskManagerApp/venv` (Activated)
- Installed: `fastapi`, `uvicorn`, `httpx`, `pytest` (Refer `TaskManagerApp/requirements.txt`)
- Reference Roadmap: `../PLAN.md`
- Skills reference: `../Skills.md`

### 🎯 Block 1 Learning Objectives:
1. **ASGI Server Concept**: Uvicorn kya hai aur traditional WSGI (like Django/Flask) se kaise alag aur fast hai?
2. **App Instance & Path Operation Decorator**: `app = FastAPI()` aur `@app.get("/")` ka internal working mechanism kya hai?
3. **Running Dev Server**: `uvicorn main:app --reload` command ke har ek part ka matlab kya hai (`main`, `app`, `--reload`)?
4. **Automatic Interactive Documentation**: Swagger UI (`http://127.0.0.1:8000/docs`), ReDoc (`http://127.0.0.1:8000/redoc`), aur OpenAPI schema (`/openapi.json`) kaise aur kyun bina kisi configuration ke generate hote hain?

### 👨‍🏫 Agent ke liye Strict Instructions (Mentor Role):
1. **Agent action nahi lenge**: Aap khud se terminal command execute nahi karenge aur na hi files create karenge jab tak main na bolun. Aap mujhe guide karenge, code aur concept explain karenge, aur main khud likhunga/run karunga.
2. **Lego Building Block Framework (What, Why, How)**:
   - **What**: Concept ka definition aur analogy.
   - **Why**: FastAPI ise aise kyun karta hai? Traditional frameworks se better kyun hai?
   - **How**: Minimal code (`main.py`), server run karna, browser mein test karna.
3. **Pacing**: Pehle concept explain karein, fir mujhe `main.py` create karne ka step batayein, fir server run karke `/docs` explore karne ka step batayein.

Aap mujhe mentor ke taur par guide karna shuru karein Block 1 ke 'What & Why' se!
```
