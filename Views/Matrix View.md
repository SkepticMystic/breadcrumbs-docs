The _Matrix View_ appears on the side of the editor, and shows the **immediate outgoing neighbours** of the current note, grouped by their [[Edge Fields|field]].

![[Matrix View.png]]

On the right side of each link, you'll see an `x` or `i`, indicating if that edge is [[Explicit Edge Builders|explicit]] or [[Implied Edge Builders|implied]]. Hover over the icon to see the [[Concepts#Edge Attributes|source]] of real edges, and the [[Concepts#Edge Attributes|kind]] of implied edges (as well as the [[Implied Relation Rounds|round]] they were added in).

## Settings

Change under `Settings > Views > Matrix`:

- **Collapse**: Collapse each group of fields by default
- **Custom Field Sorting**: When enabled, sort the field groups in the matrix by a custom order you define
- **Field Order**: (Visible when Custom Field Sorting is on) Set the exact order in which [[Edge Fields|edge fields]] appear in the matrix
- **Sort**: Change the [[Concepts#Edge Sorters|edge sorter]] used for the items within each field group
- **Show Attributes**: Choose which [[Concepts#Edge Attributes|edge attributes]] show (when hovering the `x`/`i` icon)
- **Field Groups**: Choose which [[Field Groups|field groups]] are shown
- **Lock View**: Lock the matrix view to a specific file, so it doesn't change as you navigate
- **Lock Path**: The file path to lock the matrix view to (overrides the current note)
- **Note Display Options**: Three toggles — **Folder**, **Extension**, and **Alias** — that control how note links are displayed in the matrix
