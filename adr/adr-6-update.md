# ADR 6: Update

Date: 2024-02-13

## Status
Accepted

## Context
Managing updates for applications installed on numerous devices in a hospital setting can be challenging and time-consuming. Manual updates may not be feasible, and ensuring all devices are up to date with the latest software is crucial for security and functionality.

## Decision
Implement an update server and mechanism to facilitate the seamless updating of applications across all devices in the hospital. This will allow for centralized control and efficient distribution of updates without the need for manual intervention on each individual device.

## Consequences

### Positive
- Centralized Control: The update server enables centralized management of app software, ensuring consistency across all devices.
- Quick Response to Critical Issues: The update mechanism allows for rapid deployment of critical bug fixes or updates, enhancing system reliability and security.

### Negative
- Dependency on Internet Access: The update process requires internet connectivity, which may pose a challenge in environments where internet access is limited or unreliable.

### Risks
- Internet Dependency: In scenarios where internet access is unavailable or unstable, the update process may be disrupted, potentially leading to devices running outdated software and security vulnerabilities.
