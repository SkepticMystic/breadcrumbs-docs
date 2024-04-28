This command creates a new note, and adds a Breadcrumbs edge to it from the current note. This is useful for quickly creating a new note in the context of the current note.

For example, if you're currently on your `[[Projects Overview]]` note, you can run the **Thread by field: down** command to create a new project note from the current note. By default, the new note will be called `[[down of Projects Overview]]`, but you can customise the template.

After running the command, Breadcrumbs will "leave a crumb" pointing to the newly created note:

**Projects Overview.md**

```md
---
down: "[[down of Projects Overview]]"
---

## Projects

...
```

## Settings

Change under `Settings > Commands > Threading`

- **Destination**: Choose where to write the edges to. Either as [[Typed Links#Frontmatter Links|frontmatter links]], [[Typed Links#Dataview Links|Dataview links]], or none
- **Target Path Template**: Choose a template for the name (path) of the new note. This can include placeholders for:
	- `{{source.folder}}`: The folder of the current note
	- `{{source.path}}`: The path of the current note
	- `{{source.basename}}`: The basename of the current note
	- `{{attr.field}}`: The Breadcrumbs [[Edge Fields|field]] used to thread the new note
	- e.g. `{{source.folder}}/{{attr.field}} {{source.basename}}`
