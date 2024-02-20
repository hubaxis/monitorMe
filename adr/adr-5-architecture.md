# ADR 2: Proxy

**Date**: 2024-02-13

## Status
Proposed

## Context
During the requirements analysis phase, the team identified several crucial architectural characteristics for the system: Availability, Fault Tolerance, and Deployability. We chose the event-driven architecture as the most suitable option.
## Decision
Use event-driven architecture

## Consequences

### Positive
- Availability
- Fault tolerance
- Deployability
- Performance

### Negative
- Event-driven architectures have more complexity,

### Risks
- Complex event routing logic 
