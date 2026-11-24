---
name: app-dev
description: Use this skill to find out how to build maintainable applications
---

When building applications its not good enough to make an application that works. Considerations need to be made for long-term maintainability and debuggability. This skill summarizes these considerations and provides a playbook for building applications.

## Version control

Code should be written in a way that confines changes to localized regions. This makes the version control history easily reviewable.

**Use anchoring comments** Anchoring comments act as an invariant between versions allowing the diff algorithm to easily separate changes. Anchoring comments should be a minimum of 3 lines and are semantically similar to a heading in a document.

```py
#
# Date formatters
# 
```

## Logging

Logging should provide a breadcrumb trail that can be followed during a debugging session.

**Log first** Logging needs to be in place prior to an issue happening. Adding logging afterward only delays finding and fixing issues. So, all production ready code must have logging.

**Log all major state changes** Bugs are most likely to occur during major state changes. Log the current state and what changes are being made to it.

```py
logger.debug("Updating article record %s, setting published = %s", article.id, published)
```

**Logging landmarks** Logging should include landmarks, keywords or phrases that uniquely identify the code that is running. This creates a cross referencing point between the logs and the code.

```py
logger.debug("Starting reconciliation")
``` 
