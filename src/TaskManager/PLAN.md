# Spec & Lego-Block Learning Roadmap: Task Manager API (FastAPI)

Building a complete, production-grade understanding of **FastAPI** from scratch using a step-by-step **Lego Building Block** approach.

---

## 🎯 Pedagogical Philosophy & Role Definition

> [!IMPORTANT]
> **Mentor-First Rule**: The agent will **NOT** run commands or modify project files without explicit confirmation. Every single block will follow the **What → Why → How** framework before anything is built. The user writes or approves each line of code so you gain 100% confidence in FastAPI.

```
       WHAT? (Concept / Real-world analogy)
         │
         ▼
        WHY? (Why does FastAPI do it this way? Problem it solves)
         │
         ▼
        HOW? (Minimal Lego code block, interactive test, verification in /docs)
```

---

## 🗺️ Capability Map: Lego Building Blocks

| Lego Block # | Module ID | Core Concept / Responsibility | What You Will Master |
|---|---|---|---|
| **Block 0** | `env-setup` | Python Virtual Environment & Dependencies | `venv`, `pip`, `fastapi`, `uvicorn` |
| **Block 1** | `hello-fastapi` | First App, ASGI Server & Auto Docs | `@app.get("/")`, Uvicorn reload, Swagger UI (`/docs`), ReDoc (`/redoc`) |
| **Block 2** | `type-system` | Python Type Hinting & In-Memory Storage | `int`, `str`, `bool`, `Optional`, In-memory Dicts/Lists (FastAPI's engine) |
| **Block 3** | `pydantic-schemas` | Data Validation & Serialization | Pydantic `BaseModel`, Request bodies vs Response schemas, Field validation |
| **Block 4** | `read-routes` | Path Parameters vs Query Parameters | `@app.get("/tasks")`, `@app.get("/tasks/{id}")`, query filters (`?completed=true`) |
| **Block 5** | `write-routes` | Creation, Updates & Status Codes | `@app.post("/tasks", status_code=201)`, `@app.put`, `@app.delete(status_code=204)` |
| **Block 6** | `error-handling` | Custom HTTP Exceptions | `HTTPException(status_code=404, detail="...")`, input error responses (422 Unprocessable Entity) |
| **Block 7** | `testing-suite` | API Testing without running the server | `pytest`, `fastapi.testclient.TestClient` |

---

## 📋 Specification (Phase 1: Spec-Driven Development)

### 1. Objective
Build an in-memory RESTful Task Manager backend in Python using **FastAPI** and **Pydantic**.
- Users can create, read, update, delete, and filter tasks.
- Serves as the ultimate hands-on playground to master FastAPI fundamentals.

### 2. Tech Stack & Commands
- **Python**: 3.9+
- **Framework**: `fastapi`
- **ASGI Server**: `uvicorn[standard]`
- **Data Validation**: `pydantic`
- **Testing**: `pytest`, `httpx`

**Commands**:
- Create Virtualenv: `python3 -m venv venv`
- Activate Virtualenv: `source venv/bin/activate`
- Install dependencies: `pip install fastapi "uvicorn[standard]" pytest httpx`
- Run Dev Server: `uvicorn main:app --reload --port 8000`
- Run Tests: `pytest -v`

### 3. Project Structure
Clean modular structure inside `TaskManagerApp/`:
```
TaskManager/
├── TaskManagerApp/
│   ├── main.py              # FastAPI app instance, route registration
│   ├── models.py            # Pydantic schemas (TaskBase, TaskCreate, TaskResponse)
│   ├── database.py          # In-memory database store (List/Dict helper functions)
│   └── test_main.py         # Pytest test cases using TestClient
├── requirements.txt         # Pinned project dependencies
├── PLAN.md                  # Complete roadmap and architecture specification
└── README.md                # Documentation & API usage instructions
```

### 4. Code Style & Standards
- **Explicit Type Annotations**: Every function parameter and return type must be annotated.
- **Pydantic V2 idiomatic models**: Clear field typing and default values.
- **Clean RESTful URLs**: Nouns for resources (`/tasks`), proper HTTP verbs (`GET`, `POST`, `PUT`, `DELETE`).

```python
# Style Example
from fastapi import FastAPI, HTTPException, status
from pydantic import BaseModel

app = FastAPI(title="Task Manager API")

class TaskResponse(BaseModel):
    id: int
    title: str
    completed: bool

@app.get("/tasks/{task_id}", response_model=TaskResponse, status_code=status.HTTP_200_OK)
def get_task(task_id: int) -> TaskResponse:
    ...
```

### 5. Testing Strategy
- Unit & integration tests for all CRUD endpoints using `fastapi.testclient.TestClient`.
- Verify:
  - 200 OK for valid fetches
  - 201 Created for valid task creation
  - 404 Not Found when requesting non-existent tasks
  - 422 Unprocessable Entity for schema validation failures

### 6. Boundaries
- **Always do**: Explain the *What, Why, and How* before any code. Test each Lego block on Swagger UI (`/docs`).
- **Ask first**: Before writing any file or running any terminal command.
- **Never do**: Auto-generate full codebases at once. Don't skip foundational concepts (type hints, ASGI, decorators).

---

## 🚀 Step-by-Step Learning Progression

### Block 0: Environment Setup
- **What**: Virtual environment (`venv`) aur dependencies.
- **Why**: Kyun global Python environment ko pollute nahi karna chahiye aur dependencies ko project-level isolate karna zaroori hai.
- **How**: `python3 -m venv venv`, `source venv/bin/activate`, aur `pip install fastapi "uvicorn[standard]"`.

### Block 1: Hello FastAPI & Swagger UI
- **What**: First `@app.get("/")` route aur ASGI server (`uvicorn`).
- **Why**: FastAPI synchronous aur asynchronous requests dono handle karta hai; automatic Swagger UI `/docs` bina kisi extra configuration ke kaise generate hota hai (OpenAPI standard).
- **How**: `main.py` banana, `uvicorn main:app --reload` run karna, browser mein `/docs` open karke interactive test karna.

### Block 2: Python Type Hinting & In-Memory Store
- **What**: Type hints (`int`, `str`, `bool`, `list`, `dict`, `Optional`).
- **Why**: FastAPI Pydantic aur type hints ko use karke data validation aur documentation generate karta hai.
- **How**: In-memory list of dictionaries design karna jo temporary database ka kaam karegi.

### Block 3: Pydantic Models (The Heart of FastAPI)
- **What**: Data schemas for incoming requests and outgoing responses.
- **Why**: Agar user invalid data bhejega (jaise string instead of integer), FastAPI automatic `422 Unprocessable Entity` return karega bina code likhe.
- **How**: `TaskBase`, `TaskCreate`, `TaskUpdate`, `TaskResponse` models define karna.

### Block 4: Path Parameters vs Query Parameters
- **What**: URL ke andar dynamic value (`/tasks/{task_id}`) vs optional filter parameters (`/tasks?completed=true`).
- **Why**: REST API best practices - kab path parameter use karna hai aur kab query parameter.
- **How**: `@app.get("/tasks/{task_id}")` aur `@app.get("/tasks")` with pagination/filtering.

### Block 5: HTTP Methods, Status Codes & Error Handling
- **What**: `POST` (201 Created), `PUT` (200 OK), `DELETE` (204 No Content), aur `HTTPException` (404 Not Found).
- **Why**: Client ko accurate status codes dena RESTful architecture ka sabse bada pillar hai.
- **How**: Task add karna, update karna, delete karna, aur agar task exist na kare toh clean error raise karna.

### Block 6: Writing API Tests with TestClient
- **What**: Automated tests using `pytest` and `fastapi.testclient.TestClient`.
- **Why**: Har bar manually browser ya Postman se test karne ke bajaye single command se saare endpoints verify karna.
- **How**: `test_main.py` likhna aur `pytest` run karna.
