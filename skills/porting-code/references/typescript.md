# Typescript specific guidelines

- If the source uses exhaustive pattern matching or switch statements, use a switch + never exhaustiveness checks.
- Use functions instead of trivial classes or static method only classes when porting from object-oriented languages like Java or C#.
- Minimize the exported surface area. This is especially important when porting from languages with implicit exports like Python.
- Do not use trivial libraries like `left-pad` or `is-even`
