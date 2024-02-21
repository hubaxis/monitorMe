# ADR 7: Alerting

Date: 2024-02-13

## Status: Proposed

## Context:
The current alerting system in place utilizes push notifications, SMS, and email for notifying users of important events. However, these methods may not always be sufficient or effective in certain situations. To enhance the alerting capabilities and ensure timely response to critical events, we propose the implementation of additional physical notification systems such as voice alerting and light alerting.

## Decision:
We will integrate additional physical notification systems into the existing alerting system to provide users with more immediate and noticeable alerts. This will include features such as voice alerts and light alerts to complement the existing digital notification methods.

## Consequences:

### Positive:
- Faster reaction time: Physical notifications can grab users' attention more effectively, leading to quicker responses to critical events.
- Increased reliability: Physical notifications can ensure that alerts are noticed even in noisy or distracting environments, increasing the likelihood of timely action.

### Negative:
- Additional cost: Implementing physical notification systems will incur additional costs for hardware, integration, and maintenance.

### Risks:
- False alarms: There is a risk that false alarms could trigger unnecessary physical notifications, potentially causing disruptions or annoyance to users.
