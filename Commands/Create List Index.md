This command builds a nested markdown list of all paths in a given direction from the current note. It then copies this list to the clipboard.

For example:

```md
- [[A]]
  - [[B]]
    - [[C]]
  - [[D]]
- [[E]]
  - [[F]]
```

> [!TIP]
> The output format matches the required format for the [[List Notes]] edge source. So you can paste this list into a note, and then use it as a List Note.

## Settings

- **Hierarchy**: Choose the hierarchy to use for the list. "All" will traverse all hierarchies (while still keeping the paths separate).
- **Direction**: Choose the direction to traverse in the list.
- **Link Kind**: Choose the kind of links to use in the list. Options include "wiki", "markdown", and "none".
- **Indent**: Choose the string to use for indentation in the list (e.g. ` `, `\t`).
