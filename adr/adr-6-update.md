# ADR 6: Update

**Date**: 2024-02-13

## Status
Proposed

## Context
We assume that installing app on a lot of devices in the hospital is a big headache. Manual updating all these devices could be a problem too. Our proposal includes update mechanism to support and maintain application without reinstalling.
## Decision
Use update server and update mechanism for apps in a hospital.

## Consequences

### Positive
- Control of app software
- Quick update in case of critical bug

### Negative
- Need internet access for update

### Risks
- Internet could be unavailable, and update could be blocked.