This category of [[Implied Edge Builders]] can be thought of as a _chain_ of fields which collapse down to one field.

> [!EXAMPLE]
> For example, My parent's parent is my grandparent. This is a _transitive_ implied relation, represented with the following syntax, `[parent, parent] -> grandparent` (a chain of two `parent` fields collapses down to one `grandparent` field between the start and end nodes):
>
> ```mermaid
> flowchart LR
> 1(Me) -- parent --> 2(Mother)
> 2 -- parent --> 3(Grandfather)
> 1 -. grandparent .-> 3
> ```

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

`[up] <- down`

```mermaid
flowchart LR
	A -->|up| B
	B -.->|down| A
```

`[down] <- up`

```mermaid
flowchart LR
	A -->|down| B
	B -.->|up| A
```

### Same Sibling is Sibling

If A and B both share the same _sibling_, mark them as **siblings** as well.

`[sibling, sibling] -> sibling`

```mermaid
graph LR
	A -->|sibling| B
	B -->|sibling| C
	A -.->|sibling| C
```

### Siblings Parent is Parent

If A and B are _siblings_, then make A's **parent** B's **parent**, as well.

`[sibling, parent] -> parent`

```mermaid
graph LR
	A -->|sibling| B
	B -->|parent| C
	A -.->|parent| C
```

### Parents Sibling is Aunt/Uncle

If A's _parent_ is B, and B is the _sibling_ of C, then make C the **aunt/uncle** of A.

`[parent, sibling] -> aunt-uncle`

```mermaid
graph LR
	A -->|parent| B
	B -->|sibling| C
	A -.->|aunt-uncle| C
```

### Parents Child is Sibling

If A and B both have the same _parent_, mark them as **siblings**.

`[parent, child] -> sibling`

```mermaid
graph LR
	A -->|parent| B
	B -->|child| C
	A -.->|sibling| C
```

### Cousin is Sibling

If A and B are _cousins_, mark them as such.

`[parent, sibling, child] -> cousin`

```mermaid
graph LR
	A -->|parent| B
	B -->|sibling| C
	C -->|child| D
	A -.->|cousin| D
```
