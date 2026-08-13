---
name: immaculate-vibes
description: Use when assessing a vibe coded application. This will help you determine a go/no-go and give recommendations on how to proceed.
---

# Immaculate Vibes

You are being asked to review this vibe coded codebase. You are not being asked to fix any of the issues you find, only give recommendations.

## Process

The high level process is as follows:

1. Gather all available product documentation.
2. Ask the user questions to deepen your understanding of the application.
3. Review the code based on the quality pillars.
4. Create a report with your findings.

## Quality pillars

These are the pillars of writing high quality software. Listed in order of importance, use these as your lens to view this project.

- Security - Authentication, permissions, data exposure, and unsafe browser behavior.
- Reliability - Critical flows, route health, assertions, console errors, and broken states.
- Performance - Load behavior, responsiveness, expensive assets, and user-visible latency.
- UI/UX - Navigation, clarity, validation, content expectations, and visual cohesion.
- Accessibility - Keyboard access, semantics, labels, ARIA, contrast, and assistive technology signals.

## Process in depth

### 1. Gather available product documentation

In this phase you will look for any available product documentation. This will set the foundation for your review so find anything that may relate to the quality pillars. 

Common places to look:

- PRODUCT.md
- PRD.md
- README.md
- docs/

### 2. Ask the user questions

The product documentation may be incomplete or out of sync with the state of the current application. Ask the user questions that will help deepen your understanding of the project and its requirements. If available use the question asking tool otherwise chat with the user.

Examples of questions:

- Who needs access to this application?
- What is the plan for ongoing maintenance?
- How will you monitor this application and verify its performance and reliability?
- Where is this application going to be hosted?

### 3. Review the code

Using the information you've gathered start up subagents to review the code for each quality pillar. Keep them separate to avoid polluting the context. Task them with finding issues and providing a go/no-go assessment based on their individual quality pillar.

Each issue:

- should be a concrete and actionable issue
- includes an impact assessment of the issue
	- Assign one of these impact level to each issue: Showstopper, Critical, Moderate, or Nice to have
- includes a clear description of the issue and the relevant file name and line numbers (if any)
- provides a recommendation for a solution

### 4. Create a report

Finish by gathering all of the results from the sub agents and create an in-depth HTML based report and give a high-level summary in chat. Open the HTML report in the browser for the user to review.

Key features of the report:

- A go/no-go recommendation
- Requirements: high level summary of the product and its core requirements 
- Issues: a list of the issues found ordered by impact level most severe to least
- Other info: any other important findings that a reviewer would need

Example report:

Recommendation:
No-go

The Fourgrounds coffee ranker is a public facing thats let customers of the Fourgrounds coffee shop rank their favorite coffee beverages.

Core requirements:

- The user should be presented a list of currently available beverages at Fourgrounds
- The user should be able to drag to reorder the beverages into their preferred ranking
- The user should be able to submit their ranking and be rewarded with a reward for a free bakery item of their choice
- The user should only be able to submit their ranking once

Issues:

The user can submit multiple times on Thursdays

Impact: CRITICAL - The user can accumulate multiple free rewards.

Due to a error in the parsing of the date in `date.js` line: 42 an unhandled exception can cause the check for a previous submission to be skipped in `check-reward.js` line: 16.

Recommendation: Use the built in date parser and wrap the date parsing in a try/catch to prevent exceptions from affecting other areas of the application.

Other info:

- The `coffee-products.json` file is generated daily if products change midday this might be out of date. External consumers of the rankings should take care to validate the existence of the products.
