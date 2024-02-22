# Digital Nomads Architectural Kata by O'Reilly, Spring 2024

## Who "Digital Nomads" are
We are the solution architects and managers from [EffectiveSoft Corp.](https://www.effectivesoft.com/), a leading company in software product development services.
* [Oleg Yanovich](https://www.linkedin.com/in/yanovicholeg/)
* [Oleg Maslovsky](https://www.linkedin.com/in/oleg-maslovsky-29905a5b/)
* [Andrey Charnamys](https://www.linkedin.com/in/andrei-charnamys/)
* [Andrey Safonov](https://www.linkedin.com/in/xferra/)
* [Vladimir Shlykov](https://www.linkedin.com/in/vladimirshlykov/)
 
As long-term partner for our clients, we do more than just solve technical issues. We strive to deliver technical solutions that assist our clients in achieving their business goals. We frame business challenges in a way that reveals answers, not obstacles.

Our daily practice involves seamlessly integrating technology with architecture, crafting solutions that are efficient and perfectly tailored to our clients' needs.

## Glossary
* NFR - Non-Functional Requirement
* MVP - Minimum Viable Product

## Requirements

### Background
The global remote patient monitoring systems market [was estimated at USD 965 million in 2021 and is expected to surpass USD 5,101 million by 2030](https://www.precedenceresearch.com/remote-patient-monitoring-systems-market#:~:text=The%20global%20remote%20patient%20monitoring,forecast%20period%202022%20to%202030.), poised to grow at a compound annual growth rate (CAGR) of 20% during the forecast period 2022 to 2030. North America led the global market with the highest market share of 41% in 2020.
StayHealthy, Inc., a large medical software company located in San Francisco, California, US. is now expanding into the medical monitoring market, and is in need of a new medical patient monitoring system for hospitals that monitors a patients vital signs using proprietary medical monitoring devices built by StayHealthy, Inc.

### Goal of the system
The goal of the MonitorMe system is to provide a robust medical patient monitoring solution for hospitals. The solution will provide real-time tracking and analysis of vital signs using proprietary medical monitoring devices developed by StayHealthy, Inc. The system aims to increase patient care quality by delivering accurate and timely vital sign data, proactive alerting of potential issues, comprehensive historical data storage, and seamless integration with the MyMedicalData platform.


### Non-functional Requirements
After our [detailed analysis](artifacts/Requirements.md) of business requirements, we've defined the following NFRs for the system:

 - Availability
 - Fault tolerance
 - Recoverability
 - Deployability
 - Configurability
 - Extensibility
 - Security

### Assumptions

# Proposed Architecture

## C4 Model
### System Context diagram
### Container diagram
### Component diagrams

## Architecture Decision Records


# Project implementation approach and milestones
We propose to start implementing from a Minimum Viable Product (MVP) without external integrations. We are going to use Scrum for the development process, but we are not going to deploy the system to a clinic environment after each sprint. We will need to build a test environment (staging) where the system will get auto generated data, but the values of the parameters will be real. After the MVP is ready and all tests are passed on our staging environment, we will deploy only one instance of the system to a clinic and test it thoroughly to make sure the system gets all the parameters correctly and the notifications work properly in all users’ scenarios including corner cases. During that period medical professionals shouldn't rely on the system, and they should use their current monitoring tools in parallel to reduce the negative consequences of possible issues. Also, we will get user feedback to adjust the system to medical professionals’ needs.

| Step | Goal | Tasks                                                                                                                                                                                                                                                                                                                                                               |
|-----------|--|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Discovery and initiation**     | Project planning and infrastructure set up | - Clarify the scope of the project.<br/>- Allocate resources.<br/>- Create a high-level project plan.<br/>- Set up task tracking and communication tools.<br/>- Prepare backlog stories for 1-2 sprints. <br/>- Set up development environment for web, desktop and mobile apps. |
| **MVP Development**     |  Develop the MVP | - Develop vital signs collection. <br/>- Develop vital signs storage. <br/>- Develop User authentication for all the applications. <br/>- Develop web admin panel. <br/>- Develop desktop application for nurses stations. <br/>- Develop mobile app for medical professionals. <br/>- Implement notifications. <br/>- Develop CI/CD and system updating service. <br/>- Develop test cases and test scenarious. <br/>- Write the first version of users documentation for all the applications. | 
| **MVP Alpha Testing**     |  Test MVP on staging | - Set up staging environment. <br/>- Test the system according to test cases and test scenarious including deployment and updating. <br/>- Fix known bugs and issues. | 
| **MVP Deployment and Beta Testing** | Test MVP in a clinic. | - Deploy the system to a clinic with single nurce station.<br/>- Organize a test group of nurces and medical professionals. <br/>- Gather user feedback.  |
| **MVP Update according to Feedback** | Improve the system according to users feedback and prepare MonitorMe to release. | - Analyze user feedback and prioritize enhancements.<br/>- Implement enhancements. <br/>- Deploy updated versions of the MVP, testing the updating service simultaniously. |
| **External Integrations** | Integrate the system with MonitorThem platform. | - Implement API integration with MonitorThem. <br/>- Test MonitorThem integration to make sure the data is consistant. |
| **Release Version 1.0** |  Release the MVP with integrations. | - Test the release candidate on staging. <br/>- Launch Version 1.0 for mobile, wev and desktop applications. |
| **Support 24/7** | Provide immediate reaction to critical issues. | - Allocate a support team. <br/>- Agree on SLA conditions. <br/>- Update the system as soon as possible in case of critical issues.|
| **Scaling nurses stations** | Scale infrastructure to cover all patients in the clinic. | - Deploy new nurses stations. <br/>- Monitor system performance and scalability. |
| **Continuous Improvement and expansion** | Continuously system improvement and involving new clinics. | - Deploy MonitorMe to new Clinics. <br/>- Gather feedback from new users. <br/>- Implement enhancements based on users feedback. |

