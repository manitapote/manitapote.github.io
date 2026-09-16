---
title: "Multi-Agent System"
date: 2026-09-15
description: "Multi-Agent System"
tags: ["LLM", "AI", "Multi-Agent System"]
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
- **Plan-Based Orchestration Pattern**: A single orchestrator agent manage entire taske execution through explicit plan creation, dynamic task assignment and centralized progress monitoring. 
Control flow:
    - Plan management: Orchestrator maintains explicit task plans with assignments and dependencies.
    - Visibility: Orchestrator sees all context; other agents receive only relevant information
    - Task assignment: work distribution based on plan
    - State management: centralized in the orchestrator (plan, progress, monitoring, result evaluation).

- **Handsoff Pattern**: This is peer to peer delegation based on local knowledge. Agents make local decisions about when and to whom they should transfer control based on their understanding of the task and knowledge of other available agents.
Control flow:
    - Visibility: Each agent knows only a subset of other agents and their capabilities.
    - Turn-taking: Direct handoff
    - Decision making: Local decisions based on task needs and known agents
    - State management: Explicitly passed between agents during handoff
- **Conversation-driven Pattern (Group chat)**: All agents participate in a shared conversation where ochestration emerges by taking turns as part of dialogue rather than explicit plans or structured handoffs.
Control flow:
    - Visibility: All agents observe all messages in the shared conversation
    - Turn-taking: round-robin, random
    - Decision making: next speaker selected based on conversation context, not predetermined plans
    - State managment: Implicit in the conversation history

    - **Round-robin conversation**: agents take turns in fixed repeating order, until some termination condition is met.
    - **AI-driven conversation pattern**: AI models selects the agent to make the next turn based on current conversation context.

    Selection criteria for different patterns:
    - Task characteristics:
        - Well-defined, repeatable processes -> workflow patterns
        - Dynamic, exploratory tasks -> Autonomous patterns
        - Complex planning required -> Plan-Based Orchestration
        - Domain expertise required -> Handoff patterns

    - System requirements:
        - High predictability needed -> Workflow patterns
        - Maximum autonomy required -> AI-Driven conversation
        - Resource constraints -> Handoff patterns
        - Scalability concerns -> Parallel workflows or handoff patterns

    - Implementation consideration:
        - Developer resources available -> workflow patterns
        - Rapid prototyping needed -> Conversation-driven patterns
        - Production reliability critical -> workflow patterns with explicit task management
        - Human oversight required -> Any pattern + Human delegation


#### Human Delegation Patterns

- LLM-Based Delegation: relies on agent reasoning to determine escalation needs.
- Rule-Based Delegation: uses explicit triggers defined in code.

#### UX design for multiagent system
- This is important as it acts as the human intervention point.
- Interruptibility, help understand what user can do, communicate the cost of agent actions, allow suers to decide when agents can act
- Observability and provenance: ensure users can observe/trace agent actions.

