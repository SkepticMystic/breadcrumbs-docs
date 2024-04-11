Breadcrumbs adds a new codeblock language, `breadcrumbs`. Currently, this can be used to render a tree of all paths in a given direction from the current note (similar to the [[Tree View]], or a [mermaid](https://mermaid.js.org) graph of the same data. The basic syntax is:

```yaml
type: tree
dirs: down
depth: 0-3
sort: basename asc
```

The above example would render a markdown list of all paths going _down_ from the current note, up to a depth of 3, sorted by the basename of the notes, in ascending order.

![[view.codeblock.tree.png]]

> [!WARNING]
> Although it appears similar, the syntax used is **not** YAML. Currently, the `key: value` pair is simply split at the colon : and the items trimmed.

## Fields

The following fields can be added to the codeblock to customise the output. Optional fields are marked with a `?`, and their default values are shown in `(parentheses)`.

### `type`

Type: `type?: (tree) | mermaid`

How to visualise the results.

### `dirs`

Type: `dirs?: up | (down) | same | prev | next`

Filter edges by a given direction

### `fields`

Type: `fields?: string`

Filter edges by a list of fields (comma-separated)

### `title`

Type: `title?: string`

Add a title above the codeblock

### `depth`

Type: `depth?: <number>-<number>`

Filter edges by a depth range. For example:

- `1-3` would show all paths between 1 and 3 levels deep.
- `3-` would show all paths 3 levels deep and deeper.
- `-3` would show all paths 3 levels deep and shallower.

By default, all depths are shown.

### `flat`

Type: `flat?: true | (false)`

Flatten the nested results into a flat list.

### `dataview-from`

Type: `dataview-from?: string`

Filter edges by a [Dataview](http://blacksmithgu.github.io/obsidian-dataview/) query.

### `show-attributes`

Type: `show-attributes?: string[]`

Show specific attributes about each edge in the tree/mermaid-chart. Give a comma-separated list of values. Options include:

- `hierarchy_i`: Which hierarchy the edge is from.
- `dir`: The direction of the edge.
- `field`: The field of the edge.
- `explicit`: Whether the edge is explicit or implied.
- `source`: The [source](#explicit-edge-sources) of the edge.
- `implied_kind`: The kind of [implied relation](#implied-relationships) the edge is.
- `round`: The round the implied edge was added in.

### `sort`

Type: `sort?: <field> (asc) | desc`

Used to sort the results. The available fields are:

- `basename` sorts by the basename of the note.
- `path` sorts by the full path of the note.
- `field` sorts by the field value of the note.
- `explicit` sorts by the explicitness of the edge.
  - Uses `source` as a tiebreaker for explicit edges, and `implied_kind` for implied edges.

There are more complex sort fields as well:

- `neighbour-field:<field>` sort by the _path_ of the first neighbour of the note in the given `<field>`.
  - Useful for sorting by the `next` neighbour.

### `mermaid-direction`

Type: `mermaid-direction?: LR | RL | TB | BT`

The direction of the mermaid graph (if `type: mermaid`). If you don't give a value, Breadcrumbs will choose one based on the `dir` field.

### `mermaid-renderer`

Type: `mermaid-renderer?: (dagre) | elk`

The renderer to use for the mermaid graph.

- `dagre` is the default renderer, and is more stable.
- `elk` is more experimental, but can handle larger graphs.
