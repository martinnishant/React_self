# 🧠 ReAct Agent Action Parser  

This project implements a simple **action parser** for an agent loop based on the **ReAct (Reasoning + Acting)** framework.  

In ReAct-style prompting, an LLM produces structured outputs like:  

---

## 📌 What It Does
- **Parses Agent Outputs**  
  - Extracts the **Action name** (tool to call)  
  - Extracts the **Action input** (query or command for the tool)  
- **Detects Final Answer**  
  - Recognizes when the agent has completed reasoning and is ready to respond.  

---

## ⚙️ How It Works
```python
import re

# Regex to capture "Action: ToolName: input"
action_re = re.compile(r"^Action: (\w+): (.*)")

text = "Action: Search: what is AI?"
match = action_re.match(text)

if match:
    tool_name = match.group(1)   # → "Search"
    tool_input = match.group(2)  # → "what is AI?"
    print(tool_name, tool_input)


---

👉 Do you want me to also include an **example of extending it to parse `Final Answer:`** so your README shows both cases (tool calls + final answer)?
