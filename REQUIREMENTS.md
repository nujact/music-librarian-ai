# Project Requirements

## Overview
This project will address several key pain points currently faced by a community orchestra librarian. Managing a large library of sheet music is burdensome due to the varying nature of different music pieces, how they are scored, metadata about the pieces, and how the pieces are broken out into instrument sections.

It can be very time consuming to attempt to collect and categorize the music pieces at the moment of acquisition due to the varying nature of needed sectional components as the orchestra changes over time or modified one-time focus of a specific concert.

## Business Requirements
### Goals
- Provide the ability to query in English across the digital library of music
- Provide method of easily growing of the library by adding additional pieces of sheet music with minimal metadata collection
- Provide assistance with musical score piece research for planning themes of future concerts
- As a future stretch goal, provide the ability to re-score pieces to shift/separate/combine parts for not-included instrument scores, and add them to the library

## Technical Requirements
### Goals
- Provide free open-source AI for research, text generation, and English language interaction
- Provide web interface for easy interaction with AI
- Provide AI with RAG (Retrieval Augmented Generation) access to existing PDF music library
- Provide 2 factor authentication for access to application
- Provide least cost possible by limiting resources used to minimal when no research is needed
- Provide security around all components to protect against copyright infringement 
- Provide IAC for entirety of application

### Stakeholders
- Orchestra Librarian
- Orchestra members
- System Architect
- Software engineer
- DevSecOps engineer

## Functional Requirements
### Core Features
#### Prototype Phase
1. Prototype open-source AI running LLM model that can read music 
2. Prototype AI with RAG access to private PDF collection of music
3. Prototype simple web interface with query access to AI

#### Infrastructure Phase
1. Design system architecture that covers business and technical requirements
    - 2 factor authentication design, maybe IP and password
2. Implement IAC using Terraform to mount infrastructure in AWS
    - Domain name registration for easy user access
3. Implement secrets management for required tokens that cannot be stored in GitHub
    - OAuth 2.0 API key for Google Drive

#### UAT Phase
1. Implement UAT release of application, aka deploy stable version for UAT with orchestra library access
2. Invite stakeholders in to use application and provide feedback
3. Incorporate stakeholder feedback into application

#### Elastic expense phase
1. Implement near zero expense tear down of infrastructure, aka elastic shrink or timed auto removal
   - UAT and TEST environments exist, start shrinking them to zero
   - Unsure of best method to manage shrink / tear down
2. Implement build out of on-demand of infrastructure, aka elastic growth
3. May need to implement Librarian only GUI for on-demand grow / shrink

#### Prod Release
1. Implement production release, aka rename UAT to Prod
2. Cleanup dev resources


### User Interface
- [Describe UI requirements]
- [Include mockups or wireframes if available]

### User Experience
- [Describe UX requirements]
- [Include user flow diagrams if available]

## Technical Requirements
### System Architecture
- [Describe system architecture]
- [Include architecture diagrams if available]

### Technology Stack
- Frontend:
  - [List frontend technologies]
- Backend:
  - [List backend technologies]
- Database:
  - [List database technologies]
- Infrastructure:
  - [List infrastructure requirements]

### Performance Requirements
- [List performance metrics]
- [Include benchmarks if available]

### Security Requirements
- [List security requirements]
- [Include compliance requirements if applicable]

## Non-Functional Requirements
### Scalability
- [Describe scalability requirements]

### Reliability
- [Describe reliability requirements]

### Maintainability
- [Describe maintainability requirements]

### Compatibility
- [List compatibility requirements]
  - Browsers:
  - Operating Systems:
  - Devices:

## Constraints
- [List any technical, business, or regulatory constraints]

## Dependencies
- [List external dependencies]
- [List internal dependencies]

## Timeline
- [Include project timeline]
- [List major milestones]

## Resources
- [List required resources]
- [Include budget considerations if applicable]

## Risks
- [List potential risks]
- [Include mitigation strategies]

## Appendix
### Glossary
- [Define key terms]

### References
- [List relevant documents]
- [Include links to external resources]

### Change Log
| Date | Version | Description | Author |
|------|---------|-------------|---------| 