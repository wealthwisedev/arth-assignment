# 💼 Agentic AI Fund Search Assignment (FastAPI + LangGraph)

## 📌 Objective

Build a **production-grade**, **scalable FastAPI application** that integrates an **agentic AI system** using **LangGraph**, enabling intelligent search, summarization, and reasoning over mutual fund data from [MFAPI.in](https://www.mfapi.in/).

---

## 💡 Key Goals

- Build an **Agentic AI workflow** using [LangGraph](https://github.com/langchain-ai/langgraph)
- Use **mfapi.in** to retrieve real-time mutual fund data
- Enable users to ask questions like:
  - “Which large cap mutual funds performed best in the last 1 year?”
  - “Summarize HDFC Top 100 performance”
  - “Compare Axis Bluechip with ICICI Bluechip”
- Expose REST endpoints for triggering agent interactions using **FastAPI**
- Use **OpenAI (or mock)** for LLM-powered answers
- Ensure **testability**, **extensibility**, and **scalable structure**

---

## 🛠️ Tech Stack

- FastAPI
- LangGraph
- OpenAI (or compatible mock)
- MFAPI.in
- Pydantic
- Pytest
- Uvicorn

---

## 📁 Suggested Project Structure

```text
agentic-mfapi-ai/
├── app/
│   ├── agents/                  # LangGraph agents
│   ├── api/                     # FastAPI routes
│   ├── services/                # mfapi wrappers
│   ├── schemas/                 # Pydantic models
│   ├── core/                    # Configs, LLM client
│   └── main.py                  # FastAPI entrypoint
├── tests/
├── README.md
├── requirements.txt
└── .env
```

---

## ✅ Requirements

### 1. Fund Data Service
- Connect with [mfapi.in](https://www.mfapi.in/)
- Implement:
  - `get_fund_details(scheme_code)`
  - `search_funds_by_name(query: str)`
  - `compare_funds(scheme_codes: List[str])`

### 2. LangGraph Agent
- Create agentic workflow with:
  - `FundSearcher` Search into funds API
  - `Summarizer` Sumarize the final output or structure it
  - `Comparator` Basic Comparision in between funds
  - `QuestionRouter` Follow up question in case of information is not available

### 3. API Endpoints
Expose the following endpoints:
```
GET /funds/search?q=bluechip 
GET /funds/{scheme_code}
POST /funds/compare
POST /ai/query
```

### 4. AI Questioning
Use OpenAI to:
- Summarize fund performance
- Answer natural language questions via `/ai/query`

### 5. Testing
- Unit test services, LangGraph agent logic
- Use FastAPI's test client

---

## 🧠 Example Prompt

POST `/ai/query`:

```json
{
  "question": "Compare SBI Bluechip with ICICI Bluechip fund"
}
```

Example response:
```json
{
  "summary": "SBI Bluechip has performed better over 3 years, while ICICI has had steadier NAV returns..."
}
```

Bonus Features
- Use StreamingResponse for AI answers

---

### 📘 **Evaluation Criteria with Points**


# 🧪 Evaluation Criteria & Grading

## 🎯 Total Score: **100 Points**
```markdown
| Task                                                                                 | Max Points |
|--------------------------------------------------------------------------------------|------------|
| ✅ Implement Mutual Fund Service (mfapi.in integration)                              | 15         |
| ✅ Create LangGraph-based Agentic AI system with modular graph design                | 25         |
| ✅ Expose FastAPI endpoints with OpenAPI docs                                        | 15         |
| ✅ Integrate OpenAI (or mock) for intelligent responses                              | 10         |
| ✅ Implement `POST /ai/query` to handle fund-related questions via agents            | 10         |
| ✅ Unit tests for services and agents using Pytest                                   | 10         |
| ✅ Clean, scalable code structure following SOLID principles                         | 10         |
| ✅ Bonus: streaming AI responses                                                     | +10        |
```
---

## ⏳ Time-Based Submission Bonus
```markdown
| Submission Time              | Bonus Points | Notes                                      |
|------------------------------|--------------|--------------------------------------------|
| 📅 Same day (within 24 hrs)  | +30 pts      | Exceptional speed – clean, working version |
| 📅 Within 3 days             | +20 pts      | Solid turnaround time                      |
| 📅 Within 7 days             | 0 pts        | Still acceptable, no bonus                 |
| 🐢 After 7 days              | -40 pts      | Late penalty unless otherwise justified    |
```
---

## 🧮 Final Score Calculation

Final Score = Task Points + Bonus Features + Time Bonus (or - Late Penalty) Max Possible = 100 + 10 (bonus tasks) + 30 (early bonus) = ✅ 140 / 140


