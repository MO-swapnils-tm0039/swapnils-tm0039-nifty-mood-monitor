# Prompts Log

## Prompt 1: Phase 1 Inception & Workflow Setup

```text
Phase 1: Inception 
  
Brownfield Application 
 
 
Your Role: You are an expert application architect and are tasked to create a component 
representation of this application and write it in a md files. Plan for the work ahead and 
write your steps in an md file (component-architecture.md) with checkboxes for each 
step in the plan. If any step needs my clarification, add a note in the step to get my 
confirmation. Do not make critical decisions on your own. Upon completing the plan, ask 
for my review and approval. After my approval, you can go ahead to execute the same 
plan one step at a time. Once you finish each step, mark the checkboxes as done in the 
plan. For plan create plan.md file. Task: Capture all the entities, repository, dataflow and 
front end components. Create a functional description of what the component does. For 
every component, capture the link to the actual file also. Use Mermaid diagrams for 
better visual presentation in .md files. 
 
 
1 Create Project Directory Structure 
We will work on building an application today. For every front end and backend component 
we will create a project folder. All documents will reside in the aidlc-docs folder. Throughout 
our session I'll ask you to plan your work ahead and create an md file for the plan. You may 
work only after I approve said plan. These plans will always be stored in aidlc-docs/plans 
folder. User stories must be stored in the aidlc-docs/stories folder. Architecture and Design 
documents must be stored in the aidlc-docs/construction/design folder. All implementation 
code must be in aidlc-docs/construction/code folder. All prompts in order must be stored in 
the aidlc-docs/prompts/prompts.md file. Confirm your understanding of this prompt. 
Create the necessary folders and files for storage, if they do not exist already. 
  
Step 1.1: Create Inception Plan & User Stories 
Your Role: You are an expert product manager and are tasked with creating well defined user 
stories that becomes the contract for developing the system as mentioned in the Task section 
below. Only focus on the user stories and do not worry about technical details. Plan for the 
work ahead and write your steps in an md file at aidlc-docs/plans/inception-plan.md with 
checkboxes for each step in the plan. If any step needs my clarification, add a note in the step 
to get my confirmation. Do not make critical decisions on your own. Upon completing the 
 
plan, ask for my review and approval. After my approval, you can go ahead to execute the 
same plan one step at a time. Once you finish each step, mark the checkboxes as done in the 
plan. Your Task: Our mission is to address a critical challenge faced by investors who 
struggle to make effective investment decisions aligned with their financial objectives. We 
propose developing a goal-based investment platform that revolutionizes how individuals 
approach their financial planning. By seamlessly integrating goal setting, automated 
calculations, and dynamic portfolio management, our platform will empower users to define, 
track, and achieve their specific financial aspirations, whether it's buying a home, planning 
for retirement, funding education, or saving for a dream vacation. The platform will feature 
intuitive goal templates, smart SIP calculations, risk-optimized fund recommendations, all 
while allowing users to manage multiple financial objectives simultaneously. This solution 
directly addresses the market gap in personalized, goal-oriented investment management and 
positions us to capture a significant share of the growing digital investment market. Once I 
approve the inception plan then write the user stories to aidlc-
docs/stories/overview_user_stories.md. 
  
  
Step 1.2: Create Unit of Work 
Your Role: You are an expert software architect and are tasked with grouping the MVP user 
stories into multiple units that can be built independently as mentioned in the Task section 
below. Plan for the work ahead and write your steps in an md file (aidlc-docs/plans/uow-
plan.md) with checkboxes for each step in the plan. If any step needs my clarification, add a 
note in the step to get my confirmation. Do not make critical decisions on your own. Upon 
completing the plan, ask for my review and approval. After my approval, you can go ahead to 
execute the same plan one step at a time. Once you finish each step, mark the checkboxes as 
done in the plan. Your Task: Refer to the user stories in, /aidlc-
docs/stories/overview_user_stories.md file. Group the MVP user stories into multiple units 
that can be built independently. Each unit contains highly cohesive user stories that can be 
built by a single team. The units must be loosely coupled with each other. For each unit, write 
their respective user stories and acceptance criteria in individual .md files in the /aidlc-
docs/units/ folder. Do not write the technical systems design yet. Create an integration 
strategy document /aidlc-docs/units/integration_strategy.md which will detail the 
communication contracts between all units. Include an overall application architecture 
diagram and data flow diagram in the integration strategy document. For front-end create a 
separate unit of work. 
  
Phase 2 Construction 
  
Step 2.1: Create Construction Plan & Domain Model 
  
Your Role: You are an expert software architect and are tasked with designing a unit of the 
software system. Refer to the Task section for more details. Plan for the work ahead and write 
your steps in an md file (aidlc-docs/plans/{unit}/construction-plan.md) with checkboxes 
for each step in the plan. If any step needs my clarification, add a note in the step to get my 
confirmation. Do not make critical decisions on your own. Upon completing the plan, ask for 
my review and approval. After my approval, you can go ahead to execute the same plan one 
step at a time. Once you finish each step, mark the checkboxes as done in the plan. Your 
Task: Refer to /aidlc-docs/units/{unit}.md file, which represents a software unit with the 
corresponding user stories. Also, refer to aidlc-docs/units/integration_strategy.md file for 
integration details with other units. Create a component level design for this component using 
hexagonal architectural style. Write the design details in /aidlc-
docs/construction/design/{unit}/domain_model.md file. This is a design activity only so 
make sure no code samples/stubs should be generated and use mermaid diagrams wherever 
required. 
  
 
Your Role: You are an expert software architect and are tasked with designing a unit of the 
software system. Refer to the Task section for more details. Plan for the work ahead and write 
your steps in an md file (aidlc-docs/plans/investment-engine-unit/construction-plan.md) 
with checkboxes for each step in the plan. If any step needs my clarification, add a note in the 
step to get my confirmation. Do not make critical decisions on your own. Upon completing 
the plan, ask for my review and approval. After my approval, you can go ahead to execute the 
same plan one step at a time. Once you finish each step, mark the checkboxes as done in the 
plan. Your Task: Refer to /aidlc-docs/units/investment-engine-unit.md file, which 
represents a software unit with the corresponding user stories. Also, refer to aidlc-
docs/units/integration_strategy.md file for integration details with other units. Create a 
component level design for this component using hexagonal architectural style. Write the 
design details in /aidlc-docs/construction/design/ investment-engine-
unit/domain_model.md file. This is a design activity only so make sure no code 
samples/stubs should be generated and use mermaid diagrams wherever required. 
 
 
Step 2.2 Create Development Plan & execute 
  
Your Role: You are an expert software developer and is tasked to create a plan for 
implementation of a component. Refer to task section for more details. Plan for the work 
ahead and write your steps in an md file (aidlc-docs/plans/{unit}/development-plan.md) 
with checkboxes for each step in the plan. If any step needs my clarification, add a note in the 
step to get my confirmation. Do not make critical decisions on your own. Upon completing 
the plan, ask for my review and approval. After my approval, you can go ahead to execute the 
same plan one step at a time. Once you finish each step, mark the checkboxes as done in the 
plan. Your Task: Refer to /aidlc-docs/construction/design/{unit}/domain_model.md which 
is the design document for the component and create a development plan in development-
plan.md as per design. Assume that actual implementation shall be very simple and intuitive. 
Python shall be the programming language for back-end and static HTML for front-end. 
Assume the repositories are in-memory.  
  
  
 
Next Prompt: 
Execute the development plan for {unit}, generate the classes in respective individual files 
and keep them in the app/ directory. Create a simple demo script 
that can be run locally to verify the implementation. 
  
 
 
============================END OF PROMPTS======================
```
