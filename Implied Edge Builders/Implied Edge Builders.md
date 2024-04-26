---
aliases:
  - implied
---

By [[Explicit Edge Builders|adding edges]] to the Breadcrumbs graph, you've created various _explicit_ relationships: "Note A is the _parent_ of note B", or "note C has 3 _children_: D, E, and F". But this also _implies_ some relationships. For example, if `Father` is the _parent_ of `Daughter`, then it's _implied_ that `Daughter` is the **child** of `Father`!

```mermaid
flowchart LR
	1(Daughter) -- parent --> 2(Father)
	2 -. child .-> 1
```

## Rule Kinds

Currently, all implied relationships are added in the same way, using _transitive chains_ of [[Explicit Edge Builders|explicit]] edges:

- [[Transitive Implied Relations]]
