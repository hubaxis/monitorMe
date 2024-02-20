# ADR 3: Power

Date: 2024-02-13

## Status
Proposed

## Context
In the event of a power outage, it is crucial for the hospital to have a reliable backup power source to ensure continuous data collection from patients. 

## Decision
The hospital will implement a redundant power system consisting of both a spare generator and an uninterruptible power supply (UPS) to maintain operations during power outages.

## Consequences

### Positive
- Enhanced resilience against power failures.
- Ability to continue critical operations without interruptions.
- Improved patient care and safety during power outages.
- Increased reliability of data collection processes.

### Negative
- Higher initial investment costs for purchasing and installing redundant power systems.
- Ongoing maintenance expenses for the additional equipment.
- Potential increase in physical space requirements to accommodate the backup power systems.

### Risks
- Failure of the uninterruptible power supply or spare generator could still lead to disruptions in operations.
- Inadequate maintenance or testing of the backup systems may compromise their effectiveness during emergencies.
