# ADR 1: Network

Date: 2024-02-13

## Status
Proposed

## Context
In addition to the network agnostic system decision, it is important to consider the specific implementation details and potential challenges that may arise.

## Decision
Utilize a network adapter that can create networks using high voltage lines or Wi-Fi points to ensure compatibility with various types of network infrastructures.

## Consequences

### Positive
- Flexibility to adapt to different network environments in hospitals, including older buildings with limited networking capabilities.
- Increased accessibility and connectivity for hospital staff and systems.
- Potential cost savings by utilizing existing infrastructure for network connectivity.

### Negative
- Possible performance limitations compared to traditional Ethernet networks, requiring additional optimization at the software level.
- Complexity in managing and troubleshooting network issues across diverse network types.
- Higher dependency on the reliability and stability of alternative network solutions like powerline networking or Wi-Fi.

### Risks
- Compatibility issues with certain network configurations or equipment.
- Security vulnerabilities associated with non-traditional network setups.
- Limited scalability in cases where high network traffic or specialized requirements are needed.
