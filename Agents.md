# Agents Overview: Aider

## 🧠 Agent Types

| Agent Name       | Description                               |
|------------------|-------------------------------------------|
| `DefaultAgent`   | Handles general code editing tasks        |
| `PythonAgent`    | Specialized in Python code modifications  |
| `WebAgent`       | Focused on web development tasks          |

## ⚙️ Agent Lifecycle

1. **Initialization**: Agent is initialized based on user command.
2. **Processing**: Agent processes the input and interacts with the LLM.
3. **Editing**: Agent applies the suggested edits to the codebase.
4. **Finalization**: Changes are committed using Git integration.

## 🔁 Agent Coordination

- Agents are managed by the `AgentManager` which ensures the appropriate agent is invoked based on the task.
