The Tree View appears on the side of the editor, and shows all paths with a chosen [[Field Groups|field group]], starting from the current note. By default, it shows all paths going `down`. This image shows paths going either `up` or `down`:

![[Tree View.png]]

## Settings

Change under `Settings > Views > Tree`

- **Collapse**: Fold the nested paths by default
- **Edge Sort**: Change the [[Concepts#Edge Sorters|edge sorter]] used
- **Show Attributes**: Choose which [[Concepts#Edge Attributes|edge attributes]] show
- **Field Groups**: Choose which [[Field Groups|field groups]] are shown
- **Merge Fields**: [[Concepts#Traversal|Traverse]] each [[Edge Fields|field]] separately, or all together
- **Lock View**: Lock the tree view to a specific file, so it doesn't change as you navigate
- **Lock Path**: The file path to lock the tree view to (overrides the current note)
- **Find Root**: When enabled, the tree always starts from the root of the hierarchy (walking up via the configured field groups), rather than from the current note
- **Find Root Field Groups**: The [[Field Groups|field groups]] used to walk up to the root when **Find Root** is enabled. Defaults to `ups`
- **Note Display Options**: Three toggles — **Folder**, **Extension**, and **Alias** — that control how note links are displayed in the tree
