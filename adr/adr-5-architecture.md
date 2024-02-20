# ADR 5: Architecture

Date: 2024-02-13

## Status
Proposed

## Context
In the requirements analysis phase, key architectural characteristics such as Availability, Fault Tolerance, and Deployability were identified as critical for the system. After evaluating various options, the team has selected the event-driven architecture as the most appropriate choice.

## Decision
Adopt the event-driven architecture for the system.

## Consequences

### Positive
- Improved Availability: Events can be processed independently, enhancing system availability.
- Enhanced Fault Tolerance: Isolated event processing reduces the impact of failures on the overall system.
- Increased Deployability: Decoupled components can be deployed and scaled independently.
- Better Performance: Asynchronous event processing can improve system performance.

### Negative
- Increased Complexity: Event-driven architectures introduce additional complexity compared to traditional synchronous systems.

### Risks
- Complex Event Routing: Managing event routing logic may pose challenges and require careful design and implementation to avoid issues.

