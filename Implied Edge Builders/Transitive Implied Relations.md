This category of implied relations can be thought of as a _chain_ of fields which collapse down to one field. For example, if A is the _parent_ of B, and B is the _parent_ of C, then it's _implied_ that A is the **grandparent** of C. This is a _transitive_ implied relation. Or, in a more general syntax, `[parent, parent] -> grandparent` (a chain of two `parent` fields collapses down to one `grandparent` field between the start and end nodes).

```mermaid
flowchart LR
	1(Me) -- parent --> 2(Mother)
	2 -- parent --> 3(Grandfather)
	1 -. grandparent .-> 3
```

In the settings for this relationship:

![[transitive (parent, parent) -> grandparent.png]]

## Options

- **Edge Chain**: The chain of fields required for the rule to match
	- `[parent, parent]` in the above example
- **Closing Field**: Once a match is found, which field closes the chain off
	- `grandparent` in this example
- **Close Reversed**: Whether the close the chain from start to finish, or vice versa
	- `false` (or unchecked) in this example, because it closes from start to finish
- **Rounds**: How many [[Implied Relation Rounds|rounds]] to run the rule for
	- `1` in this example
- **Name (optional)**: Give a label to the rule. By default, the `[field] -> close` syntax will be used.

## Examples

There are many different rules you can build with this syntax

### Opposite Direction

If you have to fields `up` and `down`, you can make them semantically "opposite" of one another with the following two rules (note how this rule requires the "Close Reversed" option toggled on, so that the end node points _back_ to the start node):

- `[up] <- down`

```mermaid
flowchart LR
	A -->|up| B
	B -.->|down| A
```

- `[down] <- up`

```mermaid
flowchart LR
	A -->|down| B
	B -.->|up| A
```

### Same Sibling is Sibling

If A and B both share the same _sibling_, mark them as **siblings** as well.

`[sibling, sibling] -> sibling`

### Siblings Parent is Parent

If A and B are _siblings_, then make A's **parent** B's **parent**, as well.

`[sibling, parent] -> parent`

### Parents Sibling is Aunt/Uncle

If A's _parent_ is B, and B is the _sibling_ of C, then make C the **aunt/uncle** of A.

`[parent, sibling] -> aunt-uncle`

### Parents Child is Sibling

If A and B both have the same _parent_, mark them as **siblings**.

`[parent, child] -> sibling`

### Cousin is Sibling

If A and B are _cousins_, mark them as such.

`[parent, sibling, child] -> cousin`
