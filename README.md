    Orchestrator --> Chronos
    Orchestrator --> Daemon

    %% MODEL ROUTING
    subgraph Frontier["Frontier Model Router"]
        Fast[Low-Latency Models]
        Deep[Deep Reasoning Models<br/>LongThink]
        Tool[Tool-Reliable Models]
    end

    Orchestrator --> Frontier

    %% COGNITION
    Brain[Lex Brain<br/>Reasoning Core]
    Predictive[Predictive Intent]
    Reflect[Reflection Engine]

    Orchestrator --> Brain
    Brain --> Predictive
    Brain --> Reflect
    Reflect --> Brain

    %% EXECUTION
    Mission[Mission Runner]
    Queue[RQ / Task Queue]
    Worker[Background Workers]

    Orchestrator --> Mission
    Mission --> Queue
    Queue --> Worker

    %% KNOWLEDGE & OPS
    Knowledge[Knowledge Service]
    Property[Domain Ops Agents]

    Brain --> Knowledge
    Mission --> Property
    Property --> Knowledge

    %% MEMORY STACK
    subgraph Memory["4-
# Lex
Personal AI Orchestrator
