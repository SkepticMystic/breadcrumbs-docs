_Dataview Notes_ allow you to use the [Dataview plugin](https://github.com/blacksmithgu/obsidian-dataview) query engine to add edges to the graph. You can turn a note into a dataview note by adding the following to your frontmatter:

```yaml
---
BC-dataview-note-query: "<query>"
BC-dataview-note-field: "<field>"
---
```

Where `<query>` is a valid Dataview query, and `<field>` is one of your [[Edge Fields|edge fields]]. Breadcrumbs will ask Dataview for all notes that match the query, and add edges from the current note to those notes using the field you specify.

For example, the following query will add `child` edges from the current note to all notes that contain the tag `#tag` and are in the folder "Folder":

```yaml
---
BC-dataview-note-field: "child"
BC-dataview-note-query: '"#tag" AND "Folder"'
---
```

> [!TIP]
> The `query` is passed directly to the [Dataview API](https://github.com/blacksmithgu/obsidian-dataview/blob/master/src/api/plugin-api.ts) `pages` method, which you can test out in the Obsidian console with the following (press `Ctrl + Shift + I` to open the console):
>
> ```ts
> app.plugins.plugins.dataview.api.pages(
> "<query>",
> app.workspace.getActiveFile()?.path ?? ""
> );
> ```
