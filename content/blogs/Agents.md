---
title: "Agents & Tools"
date: 2026-09-1
description: "Agents"
tags: ["LLM", "AI", "Agents", "Tools"]
---

### Categories of tools
#### Knowledge augmentation
Access to latest information either through web search tools, access to social media accounts etc.

#### Capability extension
AI agents having access to small tools instead of AI solving the problems itself.

#### Tools to act based on enviroment
AI agents plans the steps itself for task completion. Drawback of autoregressive model is that they can't backtrack and they need to restart from first step if a path does not lead to goal. This path could be defined by us or AI agent decides.

**Reinforcement Learning**: This is the training process whey the agents can determine the path based on the gain at each step.

**ReAct**: Thinking (planning), take actions and then analyze observations (reflection).


### Agent Failure Modes
**Planning failures**: This is tool use failure. _Invalid tool, valid tool invalid parameters, valid tool incorrect parameter values, goal failure (agent fails to achieve the goal or solves the problem but without following the constraints)_

Evaluation:
- Out of all generated plans, how many are valid?
- For a given task, how many plans does the agent have to generate, on average to get a valid plan?
- Out of all tool calls, how many are valid?
- How often are invalid tools called?
- How often are valid tools called with invalid parameters?
- How often are valid tools called with incorrect parameter values?

**Tool failures**: Correct tool but wrong tool output, no access to right tool

**Evaluate efficiency of agent**
- How many steps does the agent need, on average, to complete a task?
- How much does the agent cost, on average, to complete a task?
- How long does each action typically take? Are there any actions that are especially time-consuming or expensive?

### Memory
**Internal knowledge**: Modle's own knowledge from the data it was trained on.
**Short-term memory**: Model's context or input to the model.
**Long-term memory**: External data sources that a model can access via retrieval.

