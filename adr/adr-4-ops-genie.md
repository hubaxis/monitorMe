# ADR 2: Proxy

**Date**: 2024-02-13

## Status
Proposed

## Context
We assume that getting data and show it in a dashboard is few piece of application. The other important pies - management nurses/doctors/schedule and sending notification.
As a prove of concept we recommend to use [OpsGenie](https://www.atlassian.com/software/opsgenie). This application allows to create doctors/nurses and schedule for them. Also this application allow to send notification via different transport(sms/push/email and etc), and has feature to escalate alarm, if it wouldn't be asknowledged on time.

## Decision
Use OpsGenie for user management and notifications

## Consequences

### Positive
- Reduce time to market

### Negative
- Our solution depends on different service

### Risks
- service could change or even die, and we can do nothing