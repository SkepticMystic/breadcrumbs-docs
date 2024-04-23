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

- **Field Groups**: Which [[Field Groups|field groups]] to include in the traversal
- **Edge Sorter**: How to order the results
- **Show Attributes**: Which [[Reference#Edge Attributes|edge attributes]] to show
- **Indent**: Choose the string to use for indentation in the list (e.g. ` `, `\t`)
- **Link Kind**: Choose the kind of links to use in the list. Options include "wiki", "markdown", and "none"
