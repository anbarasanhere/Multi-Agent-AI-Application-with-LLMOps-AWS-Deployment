# Multi-Agent AI Application with LLMOps & AWS Deployment

End-to-end LLMOps project: a tool-using AI agent (LangGraph ReAct + Groq + optional Tavily search), a FastAPI backend, a Streamlit UI, Docker packaging, and a Jenkins pipeline that scans, builds, and deploys to Amazon ECS Fargate. 

## Architecture

```mermaid
flowchart LR
  User[User] --> UI[Streamlit UI :8501]
  UI -->|POST /chat| API[FastAPI :9999]
  API --> Agent[LangGraph ReAct Agent]
  Agent --> Groq[Groq LLM]
  Agent -.->|if search enabled| Tavily[Tavily Search]
  Jenkins[Jenkins] --> Sonar[SonarQube]
  Jenkins --> ECR[Amazon ECR]
  ECR --> ECS[ECS Fargate]
```

# Workflow
<img width="1778" height="632" alt="image" src="https://github.com/user-attachments/assets/10355cd7-055b-42d3-8b50-c5fcdb519ecb" />


