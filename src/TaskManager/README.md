# 🚀 TaskManager API

> A clean, production-grade RESTful Task Management API built from scratch in Python with **FastAPI**, **Pydantic v2**, and **Pytest**, following a step-by-step **Lego Building Block** learning architecture.

[![FastAPI](https://img.shields.io/badge/FastAPI-0.128+-009688.svg?style=flat&logo=FastAPI&logoColor=white)](https://fastapi.tiangolo.com)
[![Pydantic v2](https://img.shields.io/badge/Pydantic-v2-E92063.svg?style=flat&logo=pydantic&logoColor=white)](https://docs.pydantic.dev)
[![Python](https://img.shields.io/badge/Python-3.9+-3776AB.svg?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![Tests](https://img.shields.io/badge/Tests-13%20Passed-brightgreen.svg?style=flat&logo=pytest&logoColor=white)](https://docs.pytest.org)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

---

## 📖 Table of Contents
- [Project Overview](#-project-overview)
- [Lego Building Blocks Roadmap (Table Format)](#-lego-building-blocks-roadmap)
- [Project Directory Structure](#-project-directory-structure)
- [Quick Start Guide](#-quick-start-guide)
- [API Endpoints Reference](#-api-endpoints-reference)
- [Data Models & Schema Validation](#-data-models--schema-validation)
- [Custom Error Handling & Standard Envelope](#-custom-error-handling--standard-envelope)
- [Automated Testing Suite](#-automated-testing-suite)
- [Architecture Decision Records (ADRs)](#-architecture-decision-records-adrs)

---

## 🌟 Project Overview

**TaskManager API** is a modular RESTful backend application engineered to showcase the full power of modern asynchronous Python web development using FastAPI. The project adheres to **Spec-Driven Development** and the **What → Why → How** pedagogy:

```
       WHAT? (Concept / Real-world analogy)
         │
         ▼
        WHY? (Why does FastAPI do it this way? Problem it solves)
         │
         ▼
        HOW? (Minimal Lego code block, interactive test, verification in /docs)
```

### ✨ Key Features
- **Automatic OpenAPI Documentation**: Real-time Swagger UI (`/docs`) and ReDoc (`/redoc`) generated out of the box.
- **Strict Data Validation**: Pydantic v2 schemas validating request payloads and enforcing field length constraints.
- **Rich Parameter Handling**: Type-safe Path parameters (`gt=0`) and Query parameters with filtering (`completed`) and pagination (`limit`).
- **RESTful Status Codes**: Strict adherence to HTTP standards (`200 OK`, `201 Created`, `204 No Content`, `400 Bad Request`, `404 Not Found`, `422 Unprocessable Entity`).
- **Standardized Error Envelope**: Consistent, predictable error response structure for domain exceptions.
- **Duplicate Prevention**: Case-insensitive duplicate task title validation on both task creation and updates.
- **100% Test Coverage**: Comprehensive test suite using `pytest` and `fastapi.testclient.TestClient`.

---

## 🧱 Lego Building Blocks Roadmap

Har feature ko ek independent, reusable **Lego Building Block** ke roop mein plan aur build kiya gaya hai:

| Block # | Module ID | Core Concept (What) | Rationale (Why) | Implementation Details (How) | Mastery & Artifacts |
|:---:|:---|:---|:---|:---|:---|
| **Block 0** | `env-setup` | **Virtual Environment & Dependencies** | Global Python environment ko clean aur isolated rakhna taaki dependency conflicts na ho. | `python3 -m venv venv`<br>`source venv/bin/activate`<br>`pip install fastapi "uvicorn[standard]" pytest httpx` | `venv`, `pip`, `requirements.txt` pinning |
| **Block 1** | `hello-fastapi` | **First App & ASGI Server** | Asynchronous server gateway interface (ASGI) aur automatic interactive documentation standard (OpenAPI). | `@app.get("/")`<br>Uvicorn reload server<br>Access interactive Swagger UI | `main.py`<br>`uvicorn main:app --reload`<br>Swagger UI at `/docs` |
| **Block 2** | `type-system` | **Python Type Hints & Datastore** | FastAPI ka internal engine Python type hints se request validation aur schema generation run karta hai. | Type hints (`int`, `str`, `bool`, `Optional`, `List`, `Dict`)<br>In-memory `TASKS_DB` list of dictionaries | [database.py](file:///Users/kshitizagnihotri/Project/TaskManager/TaskManagerApp/database.py)<br>`TASKS_DB: List[Dict[str, Any]]` |
| **Block 3** | `pydantic-schemas` | **Pydantic Data Validation & Serialization** | Client se invalid data rokna aur responses ko sanitize karna; automated `422 Unprocessable Entity` handling. | `BaseModel`, `Field(...)`<br>Min/max constraints (`min_length=1`, `max_length=100`)<br>`TaskBase`, `TaskCreate`, `TaskResponse`, `TaskUpdate` | [models.py](file:///Users/kshitizagnihotri/Project/TaskManager/TaskManagerApp/models.py)<br>Inheritance & `Field` validators |
| **Block 4** | `read-routes` | **Path Parameters vs Query Parameters** | RESTful routing standards: resource identify karne ke liye Path parameters, filtering/pagination ke liye Query parameters. | `@app.get("/tasks")` with `completed: Optional[bool]` & `limit: Optional[int]`<br>`@app.get("/tasks/{task_id}")` with `Path(..., gt=0)` | Path validation (`gt=0`), Query filtering, list comprehensions |
| **Block 5** | `write-routes` | **CRUD Operations, Status Codes & Error Handling** | Client ko clear HTTP feedback dena (`201` for create, `204` for delete) aur non-existent resource par proper error throw karna. | `@app.post("/tasks", status_code=201)`<br>`@app.put("/tasks/{task_id}")`<br>`@app.delete("/tasks/{task_id}", status_code=204)`<br>Custom exception handlers | [exceptions.py](file:///Users/kshitizagnihotri/Project/TaskManager/TaskManagerApp/exceptions.py)<br>`TaskNotFoundException`<br>`DuplicateTaskException` |
| **Block 6** | `testing-suite` | **Automated API Testing with TestClient** | Bina live server run kiye rapid, reproducible integration testing verify karna har route aur edge-case par. | `pytest`, `fastapi.testclient.TestClient`<br>Happy paths, 404 handling, 400 duplicates, 422 schema violations | [test_main.py](file:///Users/kshitizagnihotri/Project/TaskManager/TaskManagerApp/test_main.py)<br>13 Passing automated test assertions |

---

## 📁 Project Directory Structure

```text
TaskManager/
├── TaskManagerApp/
│   ├── .git/                 # Git repository tracking
│   ├── .pytest_cache/        # Pytest cache directory
│   ├── venv/                 # Python 3 isolated virtual environment
│   ├── main.py               # FastAPI application, route definitions & exception handlers
│   ├── models.py             # Pydantic data schemas (TaskBase, TaskCreate, TaskResponse, TaskUpdate)
│   ├── database.py           # In-memory storage mock (TASKS_DB) with pre-seeded tasks
│   ├── exceptions.py         # Custom domain exceptions (TaskNotFoundException, DuplicateTaskException)
│   ├── requirements.txt      # Fully locked and reproducible dependency manifest
│   └── test_main.py          # Pytest suite with 13 comprehensive test cases
├── BLOCK_0_PROMPT.md         # Mentor prompt for Block 0
├── BLOCK_1_PROMPT.md         # Mentor prompt for Block 1
├── BLOCK_2_PROMPT.md         # Mentor prompt for Block 2
├── BLOCK_3_PROMPT.md         # Mentor prompt for Block 3
├── BLOCK_4_PROMPT.md         # Mentor prompt for Block 4
├── BLOCK_5_PROMPT.md         # Mentor prompt for Block 5
├── BLOCK_6_PROMPT.md         # Mentor prompt for Block 6
├── PLAN.md                   # Complete pedagogical architecture & roadmap spec
├── Skills.md                 # Agent-skills registry and operating guidelines
└── README.md                 # Master project documentation
```

---

## ⚡ Quick Start Guide

### 1. Prerequisites
- Python 3.9 or higher
- Git

### 2. Setup Virtual Environment

```bash
# Navigate to the application directory
cd TaskManager/TaskManagerApp

# Create virtual environment
python3 -m venv venv

# Activate virtual environment
# On macOS / Linux:
source venv/bin/activate
# On Windows:
# venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Start the Development Server

```bash
uvicorn main:app --reload --port 8000
```

The application will start on `http://127.0.0.1:8000`.

### 5. Access Interactive API Docs
- **Swagger UI**: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)
- **ReDoc**: [http://127.0.0.1:8000/redoc](http://127.0.0.1:8000/redoc)
- **OpenAPI Schema (JSON)**: [http://127.0.0.1:8000/openapi.json](http://127.0.0.1:8000/openapi.json)

---

## 📡 API Endpoints Reference

| Method | Endpoint | Status Code | Request Body | Query / Path Parameters | Description & Rules |
|:---:|:---|:---:|:---|:---|:---|
| `GET` | `/` | `200 OK` | _None_ | _None_ | Health check & welcome message. |
| `GET` | `/tasks` | `200 OK` | _None_ | `completed: bool` (optional)<br>`limit: int` (optional, `1` to `100`) | List all tasks with optional filters and pagination. |
| `GET` | `/tasks/{task_id}` | `200 OK` | _None_ | `task_id: int` (`Path(..., gt=0)`) | Fetch single task by ID. Returns `404` if not found. |
| `POST` | `/tasks` | `201 Created` | `TaskCreate` | _None_ | Create a new task. Checks for duplicate title (case-insensitive, `400 Bad Request`). |
| `PUT` | `/tasks/{task_id}` | `200 OK` | `TaskUpdate` | `task_id: int` (`Path(..., gt=0)`) | Update an existing task partially/fully. Validates duplicate titles. Returns `404` if not found. |
| `DELETE` | `/tasks/{task_id}` | `204 No Content` | _None_ | `task_id: int` (`Path(..., gt=0)`) | Delete task by ID. Returns `404` if not found. Empty response body. |

---

## 🛡️ Data Models & Schema Validation

All models are defined using **Pydantic v2** inside [models.py](file:///Users/kshitizagnihotri/Project/TaskManager/TaskManagerApp/models.py):

```python
from pydantic import BaseModel, Field
from typing import Optional

class TaskBase(BaseModel):
    title: str = Field(..., min_length=1, max_length=100, description="Title of the task")
    description: Optional[str] = Field(default=None, max_length=500, description="Description of the task")
    completed: bool = Field(default=False, description="Completion status of the task")

class TaskCreate(TaskBase):
    """Payload schema for creating a new task."""
    pass

class TaskResponse(TaskBase):
    """Response schema returning task with server-generated ID."""
    id: int = Field(..., description="Unique identifier of the task")

class TaskUpdate(BaseModel):
    """Payload schema for partial task updates."""
    title: Optional[str] = Field(default=None, min_length=1, max_length=100)
    description: Optional[str] = Field(default=None, min_length=1, max_length=500)
    completed: Optional[bool] = Field(default=None)
```

### Validation Highlights:
- **Clean Inheritance**: `TaskCreate` and `TaskResponse` inherit core attributes from `TaskBase` ensuring DRY principles.
- **Partial Updates**: `TaskUpdate` fields are all optional; in `main.py`, `.model_dump(exclude_unset=True)` updates only fields provided by the client.
- **Length Constraints**: Tasks cannot have empty titles (`min_length=1`) or overly long titles/descriptions (`max_length=100` / `500`).

---

## 🚨 Custom Error Handling & Standard Envelope

Rather than relying on plain strings, the application uses **Domain-Specific Exceptions** paired with **FastAPI Custom Exception Handlers** to produce consistent error responses:

### 1. Custom Exceptions ([exceptions.py](file:///Users/kshitizagnihotri/Project/TaskManager/TaskManagerApp/exceptions.py))
- `TaskNotFoundException(task_id: int)`
- `DuplicateTaskException(title: str)`

### 2. Standardized JSON Envelope Format

#### 404 Not Found (Task does not exist)
```json
{
  "success": false,
  "error": {
    "code": "TASK_NOT_FOUND",
    "message": "Task with ID 9999 not found",
    "status_code": 404
  }
}
```

#### 400 Bad Request (Duplicate task title)
```json
{
  "success": false,
  "error": {
    "code": "DUPLICATE_TASK",
    "message": "A task with title 'Setup development environment' already exists",
    "status_code": 400
  }
}
```

#### 422 Unprocessable Entity (Schema validation failure)
FastAPI automatically returns Pydantic's structured validation payload detailing missing fields or violation constraints:
```json
{
  "detail": [
    {
      "type": "missing",
      "loc": ["body", "title"],
      "msg": "Field required"
    }
  ]
}
```

---

## 🧪 Automated Testing Suite

All endpoints are thoroughly verified with **Pytest** and FastAPI's **TestClient** (backed by `httpx`).

### Run the Tests

```bash
# Activate your venv first
source venv/bin/activate

# Execute pytest with verbose output
pytest -v
```

### Test Matrix Summary (13 Tests, 100% Pass)

| Test Function | Target Route | Tested Scenario | Expected Status |
|:---|:---:|:---|:---:|
| `test_read_root` | `GET /` | Root health check payload verification | `200 OK` |
| `test_create_task_success` | `POST /tasks` | Valid task creation and ID generation | `201 Created` |
| `test_create_task_invalid_payload` | `POST /tasks` | Missing required `title` field | `422 Unprocessable Entity` |
| `test_get_all_tasks` | `GET /tasks` | Retrieve pre-seeded task list | `200 OK` |
| `test_get_tasks_filter_completed` | `GET /tasks` | Filter query `?completed=true` | `200 OK` |
| `test_get_task_by_id_success` | `GET /tasks/1` | Fetch existing task by ID | `200 OK` |
| `test_get_task_by_id_not_found` | `GET /tasks/9999` | Fetch non-existent ID; error envelope validation | `404 Not Found` |
| `test_update_task_success` | `PUT /tasks/1` | Partial update of task title and completion status | `200 OK` |
| `test_update_task_not_found` | `PUT /tasks/9999` | Update non-existent task ID | `404 Not Found` |
| `test_delete_task_success` | `DELETE /tasks/2` | Successful deletion and subsequent 404 confirmation | `204 No Content` |
| `test_delete_task_not_found` | `DELETE /tasks/9999` | Delete non-existent task ID | `404 Not Found` |
| `test_create_task_duplicate_title` | `POST /tasks` | Duplicate task creation (case-insensitive) | `400 Bad Request` |
| `test_update_task_duplicate_title` | `PUT /tasks/4` | Rename task to existing title in database | `400 Bad Request` |

---

## 🏛️ Architecture Decision Records (ADRs)

Following the principles of `/documentation-and-adrs`, significant architectural decisions are recorded below:

### ADR-001: In-Memory Datastore for Foundational Learning
- **Context**: Needed an ultra-fast, zero-configuration datastore to learn FastAPI mechanics (routing, validation, status codes) without ORM overhead.
- **Decision**: Implemented an in-memory `List[Dict[str, Any]]` (`TASKS_DB` in `database.py`).
- **Consequences**: Zero database setup required, instant test execution; state resets on server reload (production will migrate to SQLAlchemy/PostgreSQL).

### ADR-002: Standardized JSON Error Envelope over Default HTTPException
- **Context**: Standard FastAPI `HTTPException` returns `{"detail": "..."}`, which provides poor machine-readability for frontend clients.
- **Decision**: Created custom domain exceptions (`TaskNotFoundException`, `DuplicateTaskException`) handled by `@app.exception_handler`.
- **Consequences**: API consumers receive uniform payloads containing `success`, `error.code`, `error.message`, and `error.status_code`.

### ADR-003: Model Hierarchy & Partial Updates via `exclude_unset`
- **Context**: `PUT` endpoints need to support updating only specified fields without overwriting omitted fields with `None`.
- **Decision**: Configured `TaskUpdate` with all optional fields and applied `.model_dump(exclude_unset=True)`.
- **Consequences**: Allows partial PATCH-like behavior cleanly within standard PUT semantics while retaining Pydantic validation.

---

## 📜 Development Standards & Guidelines
- **Type Annotations**: All function signatures specify explicit parameter types and return type annotations.
- **Status Codes**: Always use constants from `fastapi.status` (e.g., `status.HTTP_201_CREATED`) instead of magic numbers.
- **REST Conventions**: Resource-oriented plural URLs (`/tasks`) with standard HTTP verbs.
