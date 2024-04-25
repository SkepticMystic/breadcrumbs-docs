Breadcrumbs adds a new codeblock language, `breadcrumbs`. Currently, this can be used to render a tree of all paths in a given direction from the current note (similar to the [[Tree View]], or a [mermaid](https://mermaid.js.org) graph of the same data. The source is parsed as **YAML**:

```yaml
type: tree
fields: down
depth: [0, 3]
sort: basename asc
```

The above example would render a markdown list of all paths pointing _down_ from the current note, up to a depth of 3, sorted by the basename of the notes, in ascending order.

![[view.codeblock.tree.png]]

## Available Fields

The following fields can be added to the codeblock to customise the output. Optional fields are marked with a `?`, and their default values are shown in `(parentheses)`.

### `type`

**Type**: `type?: (tree) | mermaid`

How to visualise the results.

- `tree` is similar to the [[Tree View]]
- `mermaid` renders the results in a Mermaid graph

### `start-note`

**Type**: `start-note?: string`

Override the starting note of the traversal. By default, the note that the codeblock is in will be used.

### `fields`

**Type**: `fields?: string[]`

Filter edges by a list of your [[Edge Fields|edge fields]].

### `field-groups`

**Type**: `field-groups?: string[]`

Similar to the [[#`fields`]] property, but you can select multiple [[Field Groups|field groups]] instead of individual fields.

### `title`

**Type**: `title?: string`

Add a title above the codeblock.

### `depth`

**Type**: `depth?: [number] | [number, number]`

Filter edges by a depth range. For example:

- `[0, 3]` would show all paths 3 levels deep and shallower
- `[1, 3]` would show all paths between 1 and 3 levels deep
- `[3]` would show all paths _atleast_ 3 levels deep

By default, all depths are shown.

### `flat`

**Type**: `flat?: true | (false)`

Flatten the tree results into a un-nested list.

### `dataview-from`

**Type**: `dataview-from?: string`

Filter edges by a [Dataview](http://blacksmithgu.github.io/obsidian-dataview/) query.

### `show-attributes`

**Type**: `show-attributes?: EdgeAttribute[]`

Show specific [[Reference#Edge Attributes|edge attributes]] about each item in the result.

### `sort`

**Type**: `sort?: <field> (asc) | desc`

Order the results using a given [[Reference#Edge Sorters|edge sorter]].

### `mermaid-direction`

**Type**: `mermaid-direction?: LR | RL | TB | BT`

The direction of the mermaid graph (if `type: mermaid`).

### `mermaid-renderer`

**Type**: `mermaid-renderer?: (dagre) | elk`

The renderer to use for the mermaid graph.

- `dagre` is the default, and is more stable.
- `elk` is more experimental, but can handle larger graphs.
