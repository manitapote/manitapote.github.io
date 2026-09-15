---
title: "Multi-Agent System"
date: 2026-09-15
description: "Multi-Agent System"
tags: ["LLM", "AI", "Multi-Agent System""]
---


Two approaches to multi-agent orchestration:
- **Multi-agent workflow (defined orchestration)**: These systems follow pre-defined collaboration patterns where each agent has clear specified logic and roles. This is deterministic.
- **Autonomous multi-agent orchestration (ai-driven orchestration)**: The system use AI models to drive orchestration. This is dynamic system and agent collaboration is based on task requirement and itermediate results.

Multi-agent systems are most beneficial for tasks exhibiting four key characteristics: requiring planning, needing diverse expertise, involving extensive context and requiring adaptive solutions.

### Multi-agent Orchestration Patterns

#### Workflow Patterns (Explicit Control)
This is deterministic pattern where the behavior is predictable. The pattern is similar to the graph with nodes and edges.
- **Sequential Workflows**: Linear execution where each node's output feeds into the next node.
- **Conditional Workflows**: This use logic based edges to determine the next node based on conditions, enabling branhcing execution paths and dynamic routing. Example: code generation where the edges loops back to generation phase if the code test fails. This is also a supervisor workflow (a tree structure).
- **Parallel workflows**: This enables concurrent execution of independent tasks using Directed Acyclic Graphs (DAGs).

#### Autonomous Patterns (Emergent Control)
The flow of control is driven by the AI model and dynamically determined at runtime.
-**Plan-Based Orchestration Pattern**: A single orchestrator agent manage entire taske execution through explicit plan creation, dynamic task assignment and centralized progress monitoring. 
    - Plan management: Orchestrator maintains explicit task plans with assignments and dependencies.
    - Visibility: Orchestrator sees all context; other agents receive only relevant information
    - Task assignment: work distribution based on plan
    - State management: centralized in the orchestrator (plan, progress, monitoring, result evaluation).

- **Handsoff Pattern**: This is peer to peer delegation based on local knowledge. Agents make local decisions about when and to whom they should transfer control based on their understanding of the task and knowledge of other available agents.
Control flow:
    - Visibility:
    - Turn-taking:
    - Decision making:
    - State management: