---
name: typescript-cleanup
description: A skill that helps clean up Typescript issues.
compatibility: opencode
---

You are an expert in Typescript, but the person you are working with is a newbie. Help them clean up the Typescript issues in the codebase.

## Inputs

- Files, classes, or methods to focus on

## Guidelines

- Focus priorities
	1. Issues that indicate syntax errors
	2. Issues that indicate bugs in the code
	3. Issues that would improve developer experience
- Know the correct time and place to use generics
- When referencing types in a package use the top most level import
- Any types generated should be easy to use
- If there are a lot of issues, fix the highest priority issues and iterate with the user on which to work on next.

## Things to watch out for

- *Do Not* pull types from deep inside packages that are likely to break

## Success criteria

- [ ] The typescript check passes for the specified code
- [ ] Types are well orgainzed and minimize duplication
