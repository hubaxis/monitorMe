# ADR 1: Network

**Date**: 2024-02-13

## Status
Proposed

## Context
All hospital have to have an intranet network, but sometimes it's could be low quality, or even not exists(if building too old).
We plan to build network agnostic system, which will be able to work in any type of network. As ready solution we could add to our system network adapter, which will be able to create network using high voltage network, or Wi-Fi points

## Decision
Use network agnostic solution

## Consequences

### Positive
- We can provide solution for any type of hospital building

### Negative
- All other solution except ethernet will provide worse quality of network, it should be compensate by code side

### Risks
- Alternative network solution could have worse quality than necessary 