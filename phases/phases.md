# Buildout Workflow Phases

## 1 Prototype Phase []
1. Prototype open-source AI running LLM model that can perform internet research 
2. Prototype AI with RAG access to private PDF collection of music
3. Prototype simple web interface with query access to AI

## 2 Infrastructure Phase
1. Design system architecture that covers business and technical requirements
2. Implement IAC using Terraform to mount infrastructure in AWS
    - Domain name registration for easy user access
    - Define DEV, UAT, and PROD subdomains
3. Implement secrets management for required tokens that cannot be stored in GitHub
    - OAuth 2.0 API key for Google Drive

## 3 UAT Phase
1. Implement UAT release of application, aka deploy stable version for UAT with orchestra library access
2. Invite stakeholders in to use application and provide feedback
3. Incorporate stakeholder feedback into application

## 4 Elastic expense phase
1. Implement near zero expense tear down of infrastructure, aka elastic shrink or timed auto removal
   - UAT and TEST environments exist, start shrinking them to zero
   - Unsure of best method to manage shrink / tear down
2. Implement build out of on-demand of infrastructure, aka elastic growth
3. May need to implement Librarian only GUI for on-demand grow / shrink

## 5 Prod Release
1. Implement production release, aka rename UAT to Prod
2. Cleanup dev resources
