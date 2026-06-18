# LangGraph
Building langgraph concepts and end to end pipelines for Agentic AI
<img width="1134" height="438" alt="image" src="https://github.com/user-attachments/assets/f6d8ca79-e5ba-44d7-9b02-d5f6c936c530" />

- It's orchestration framework that enables you to build stateful, multi-step, and event-driven workflow using LLM. It's ideal for designing both single-agent and multi-agent agentic AI applications.

- Flowchart engine for LLMs --- Define steps(Nodes), how they're connected(edges), and logic that governs transitions.

- LangGraph takes care of state management, conditional branching, looping, pausing/resuming and fault recovery -- Feature essential for building robust, production grade AI systems.

## When to use what? 
- LangChain
    - Building simple, linear workflow - like prompt chain, summarize, or basic retrieval system.

- LangGraph
    - Use case involce complex, non-linear workflows that need:
        1. Conditional path
        2. Loops
        3. Human-in-the-loop steps
        4. Multi agent coordination
        5. Asynchronous / Event driven execution

## Still need to use LangChain?
- Yes, LangGraph is built on the top of langChain it doesn't replace it.
- Still need to use langChain components

- ➡️LangGraph handles " Workflow orchestration "
- ➡️LangChain provides " Building blocks for each step in the workflow "

## Common Workflow
- Prompt chaining
- Routing
- Parallelization
- Orchestrator Workers
- Evaluate optimizer

## Graph, Nodes and Edges
- Nodes == Task --> Python functions
- Edges == follow up task --> Direction after function execution
- Graph == Nodes & Edges --> To make workflow

## Few common terms
- State --> Shared memory throughout the workflow
    1. Accesible --> Nodes
    2. Mutable

- Reducers 
    1. Define how update for nodes are applied
    2. Each key is state can have it own reducers, which determine whether new data replaces, merges, or add to the existing value

# LangGraph Execution Model
1. Graph
    - State schema
    - Node
    - Edges
2. Compilation
    - .compile() on stategraph
3. Invokation
    - .invoke() [Initial_state]
4. Super-steps begin
    - Execution proceeds in "rounds"
5. Message Passing & Node activation
    - Nodes that receive messages become active for next round
6. Halting Conditions
    - Execution stops when:
        1. No nodes are active
        2. No messages are in transit

