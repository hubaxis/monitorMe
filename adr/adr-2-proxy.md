# ADR 2: Proxy

Date: 2024-02-13

## Status
Proposed

## Context
The decision to use a proxy device to collect data from different devices raises important considerations regarding the implementation and potential implications for the system.

## Decision
Utilize a proxy device, such as a Patient Monitor Station or a Raspberry Pi with additional controllers for IoT, to aggregate data from various devices and reduce the dependency on network quality for decision-making within the system.

## Consequences

### Positive
- Reduced impact of network quality on the system's ability to make critical decisions based on real-time data.
- Improved data aggregation and centralization for better monitoring and analysis.
- Potential for increased system reliability by offloading data collection tasks to a dedicated proxy device.

### Negative
- Increased cost associated with acquiring and maintaining additional hardware for the proxy solution.
- Dependency on the reliability and performance of the proxy device, which could introduce a single point of failure in the data collection process.

### Risks
- System downtime or data loss in the event of a failure or malfunction of the proxy device, leading to potential gaps in patient monitoring and decision-making.
- Compatibility issues between the proxy device and the various data sources, requiring additional configuration and troubleshooting.
