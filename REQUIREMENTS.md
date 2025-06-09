# Project Requirements

## Overview
This project will address several key pain points currently faced by a community orchestra librarian. Managing a large library of sheet music is burdensome due to the varying nature of different music pieces, how they are scored, metadata about the pieces, and how the pieces are broken out into instrument sections.

It can be very time consuming to attempt to collect and categorize the music pieces at the moment of acquisition due to the varying nature of needed sectional components as the orchestra changes over time or modified one-time focus of a specific concert.

## Business Requirements
### Goals
- Provide the ability to **query** in English across the **digital library** of music
  - Queries can include **metadata**, e.g. details like the title, composer, arranger, instrumentation, and publication date
  - Queries can include content contained in the **musical notation** itself, e.g. data in the symbols to represent notes, rhythms, and dynamics. Also data in the notes such as pitches, clefs like the treble and bass clef, determining which notes correspond to lines and spaces.
- Handle easily **growing the library** by adding additional pieces of sheet music with minimal metadata collection outside of the application
- Provide **assistance with** musical score piece **research** for planning themes of future concerts
- As a future stretch goal, provide the ability to **re-score pieces** to shift/separate/combine parts for not-included instrument scores, and add them to the library

## Technical Requirements
### Goals
- Provide free **open-source AI** for research, text generation, and English language interaction
- Provide **web interface** for easy interaction with AI
- Provide AI **access to existing PDF music library**
- Provide **authentication** for access to application
- Provide **least cost possible** by limiting resources used to minimal when no research is needed
- Provide **security around file storage access** to protect against copyright infringement 
- Provide **Infrastructure As Code** IAC for entirety of application

### Stakeholders
- Orchestra Librarian
- Orchestra members
- System Architect
- Software engineer
- DevSecOps engineer

## Functional Requirements
### Core Features
- Domain name to easily access AI application
- Query ability of AI application
- AI with access to digital music library
- AI with web access for research purposes

### User Interface
- There is not much GUI requirements needed.  Only simple questions or queries being asked of the AI, and it responses coming back.  A single text input box with a submit button is enough to cover the basic needs.

### User Experience
- The users will interact with the AI application in the question or query format, and read the responses.  They are technically savvy enough to copy and paste out the responses needed outside this application.  
- If existing files are referenced as part of the query response, the name and folder location are sufficient for inclusion in the response.  Users expect and interact directly with the file storage system outside of this application.
- If new files are created from the AI, it will be creating and pushing the new files into the existing document storage location and simply providing the name folder location of the new file to the user.

## Technical Requirements
### System Architecture
- This application will using off-the-shelf components mounted in the AWS cloud, and communicate via AWS networking.  OLLaMa is an excellent and free open source LLM engine, and OpenWebUI is an excellent GUI for generic LLM querying.  
- ![Music AI Architecture](./phases/2.infra/MusicAIArchitecture.jpg)

### Technology Stack
- Frontend:
  - [OpenWebUI](https://docs.openwebui.com/)
- Backend:
  - [OLLaMa](https://ollama.com/)
- Database:
  - Postgres database embedded with OpenWebUI
- Infrastructure:
  - AWS Cloud
    - VPC
    - 2 Subnets, public and private
    - Elastic IP
    - EC2
    - ECS Fargate, 2 containers
      - OpenWebUI
      - Postgres
    - ALB
    - Route53 Domain name
    - Google drive, pre-existing

### Performance Requirements
- There are no specific identified performance requirements due to the seldom and intermittent use of this application.  Also, when it is used for research, waiting several minutes for a response would be acceptable - not what to aim for, but acceptable.
- A response time of less than 30s per prompt request would be a reasonable metric to achieve.

### Security Requirements
- There is concern for the copyright infringement protection around the google drive contents, and therefore around the AI usage of those contents.  A shared AI used by people outside of the orchestra could cause risk due to the copyrighted nature of the musical scores.  To mitigate this risk, careful attention should be given to accessing google drive, and ensure the AI is privately used by this orchestra only.

## Non-Functional Requirements
### Scalability
- Scaling is not of concern for this application due to the nature of the single user - the orchestra librarian.
- Scaling is also not an issue to achieve faster response time since a metric of 30s response is acceptable.

### Reliability
- System reliability and uptime is not of concern for this application due to the intermittent nature of its use for research purposes only when planning quarterly concerts.  In fact, to reduce costs, it is likely that this application will be completely shut down during non-use.  This would require manual steps to be taken to bring the system online, requiring wait-time to begin using it.

### Maintainability
- Logs from EC2, Fargate, OLLaMa, postgres, and OpenWebUI containers should be shipped to CloudWatch for later perusal.
- To assist with debugging and system monitoring, the free tier of CloudWatch keeping the logs for 30 days and up to 5 gigs of space will be acceptable.

### Compatibility
- Known systems that will access the application
  - Browsers:  Chrome
  - Operating Systems:  None
  - Devices:  None, except maybe from Chrome on a phone

## Constraints
- The only known constraint is around the composition copyrights of the music library.  Even though the original orchestral arrangement is most likely out of copyright, the version of the composition that is in the library could be more recent and under copyright.  So care must be taken to prevent unauthorized usage or access to the drive contents, along with AI leakage.

## Timeline
- This is a side project for fun purposes only, so there is no contractual deadlines or agreed to delivery dates.

## Resources
- Budgeting for the initial prototypes is ZERO.  Building and running LLMs on local machines makes this feasible and achievable.
- Budgeting for the DEV and UAT deployments in AWS will be within the boundaries of my own pocketbook.  This means close careful inspection of expenditures and carefully reducing the footprint to zero when not actively developing the application.
- Prod release will occur to an AWS account with billing directly to the Orchestra.  Still requires careful attention to approach near zero monthly expenses.

## Phases of Development
Please see [Development Phases](./phases/phases.md) for a breakdown of epics, stories, and current state of each.
