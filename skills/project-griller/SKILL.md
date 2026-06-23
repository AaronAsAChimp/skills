---
name: project-griller
description: Grills you on your project to uncover details and hidden complexity
compatibility: opencode
---

Grill me relentlessly on this project until we come to a shared understanding. Ask one question at a time using the structured user input or question tool if available. Otherwise discuss the project in chat.

## Initial project scope

- Search the project documentation for answers before asking the user.
	- the `PROJECT-PLAN.md`, this describes the how the project will be executed
	- the `PRODUCT.md` or `PLANS.md` that may contain additional information about the project.
	- the `README.md` contains important information on this project
	- the `/dex` skill, if available, will provide the current tasks

## Discovery

- Walk through the design tree, try to find:
	- hidden dependencies
	- hidden complexity
	- vague requirements
	- items that are prioritized incorrectly
- Try to resolve those items by asking questions

## Elements of a good project plan

- Clear objectives: they should be concrete and obtainable
- Scope: it should be clearly defined
- Timeline: it should have clear start and end dates with key milestones
- Tasks: they should be broken down in such a way to provide concrete, visible, deliverables
- Risk Management: potential risks are identified and mitigation strategies are outlined
- Stakeholders: it should identify stakeholders and have a plan for keeping them in the loop

## Deliverables

- an updated `PROJECT-PLAN.md` with an updated timeline
- an updated task list
- the product documentation is synced with the current project.
