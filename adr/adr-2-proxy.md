# ADR 2: Proxy

**Date**: 2024-02-13

## Status
Proposed

## Context
To collect all data from different devices, we plan to use proxy device. It could be Patient Monitor Station or any device which will be able to get signal form external devices, or it could be raspberry pi with additional controllers for IoT. In this case quality of network will not influence on app for making decision

## Decision
Use proxy app/device

## Consequences

### Positive
- Influence of network becomes insignificant

### Negative
- In case of additional devices - cost of solution becomes bigger

### Risks
- If proxy app/device died - whole data stream about patient will be stopped