# Phases for Building Out Application

## 1 Prototype Phase
The prototype phase is all about getting an AI application running locally that can perform research off the internet and read thru a set of PDFs locally.
1. [Local AI Research](./1.prototype/1.LocalAIResearch.md) Prototype open-source AI running LLM model that can perform internet research 
2. [LLM with RAG](./1.prototype/2.LLMRAG.md) Prototype AI with RAG access to private PDF collection of music
3. [OpenWebUI](./1.prototype/3.openwebui.md) Prototype simple web interface with query access to AI

## 2 Infrastructure Phase
Design the system to achieve targeted goals, implement infrastructure as code, and setup secrets management
1. [Architecture](./2.infra/1.Architecture.md) Design system architecture that covers business and technical requirements
2. [IAC](./2.infra/2.IAC.md) Implement IAC using Terraform to mount infrastructure in AWS
    - Domain name registration for easy user access
    - Define DEV, UAT, and PROD subdomains
3. [Secrets](./2.infra/3.Secrets.md) Implement secrets management for required tokens that cannot be stored in GitHub
    - OAuth 2.0 API key for Google Drive

## 3 UAT Phase
Provide the initial version of the application to users for testing, obtain feedback, and incorporate requested changes
1. [UAT Release]() Implement UAT release of application, aka deploy stable version for UAT with orchestra library access
2. [UAT Feedback]() Invite stakeholders in to use application and provide feedback
3. [UAT Updates]() Incorporate stakeholder feedback into application

## 4 Elastic expense phase
1. [Tear Down]() Implement near zero expense tear down of infrastructure, aka elastic shrink or timed auto removal
   - UAT and TEST environments exist, start shrinking them to zero
   - Unsure of best method to manage shrink / tear down
2. [Tear Up]() Implement build out of on-demand of infrastructure, aka elastic growth
3. [Tear Up GUI]() May need to implement Librarian only GUI for on-demand grow / shrink

## 5 Prod Release
1. [Prod Release]() Implement production release
2. [Dev Cleanup]() Cleanup dev resources
