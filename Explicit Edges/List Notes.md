_List Notes_ allow you to leverage your existing bullet list structure. You can turn a note into a list note by adding the following to your frontmatter:

```yaml
BC-list-note-field: <field>
```

Where `<field>` is one of your Breadcrumbs fields. The structure of a List Note is as follows:

```md
- [[A]]
  - [[B]]
    - [[C]]
  - [[D]]
```

In this example, `A` goes down to `B` and `D`, and `B`goes down to `C` (assuming the field you used is `down`).

[![](https://mermaid.ink/img/pako:eNpVjzEPgjAQhf9Kc1NJYBB16WCiMqKDrl0u9NBG2ppyhBjCf7fKxC3v8uXlvbwJmmAIFLRdGJsnRhb1TXuRbiNr27O4BqZMFIUwYfRJD6KUxzXYytMa7OQ5W0LKFd_LKoMcHEWH1qTW6efSwE9ypEGl12B8adB-Tj4cONw_vgHFcaAchrdBpsriI6ID1WLXJ0rGcoiXZcZ_zfwFMOY_Hg?type=png)](https://mermaid.live/edit#pako:eNpVjzEPgjAQhf9Kc1NJYBB16WCiMqKDrl0u9NBG2ppyhBjCf7fKxC3v8uXlvbwJmmAIFLRdGJsnRhb1TXuRbiNr27O4BqZMFIUwYfRJD6KUxzXYytMa7OQ5W0LKFd_LKoMcHEWH1qTW6efSwE9ypEGl12B8adB-Tj4cONw_vgHFcaAchrdBpsriI6ID1WLXJ0rGcoiXZcZ_zfwFMOY_Hg)

## Field Overrides

By default, each item in the list will use the `BC-list-note-field` value to add edges. But you can override this on a per-item basis by adding the field _before_ the link.

```md
---
BC-list-note-field: down
---

- [[A]]
  - child [[B]]
```

In this example, `List Note` -down-> `A`, but `A` -child-> `B`.

[![](https://mermaid.ink/img/pako:eNoljjELwjAUhP9KeFML7aBuGQTFsTromuWR92qDTSLpK0VK_7sx3nLHx3HcCjYSg4Z-jIsdMInq7iaorF3VuUnULQrXqm0VxSVkP6p9dSrADm6kQg7VuYYGPCePjvLa-pswIAN7NqBzJEwvAyZsuYezxMcnWNCSZm5gfhMKXxw-E3rQPY5TpkxOYrr-75WX2xezITYI?type=png)](https://mermaid.live/edit#pako:eNoljjELwjAUhP9KeFML7aBuGQTFsTromuWR92qDTSLpK0VK_7sx3nLHx3HcCjYSg4Z-jIsdMInq7iaorF3VuUnULQrXqm0VxSVkP6p9dSrADm6kQg7VuYYGPCePjvLa-pswIAN7NqBzJEwvAyZsuYezxMcnWNCSZm5gfhMKXxw-E3rQPY5TpkxOYrr-75WX2xezITYI)

## `BC-list-note-exclude`

By default, the list note itself links to the top-level list items. You can exclude this behaviour by adding the `BC-list-note-exclude` field to the frontmatter of the list note.

```yaml
BC-list-note-exclude: true
```

[![](https://mermaid.ink/img/pako:eNpVjj0LwjAQhv9KuCmBdvFjySCoHXXRNcuRXG2xSSQmFCn9754fS9_lXh4ejncCGx2BhnaIo-0wZXG6mCA4K7lXoq6Fi2PguxNreViCjTyqv7vgW9koqMBT8tg7fj59LAO5I08GNFeH6W7AhJk9LDleX8GCzqlQBeXhMFPT4y2hB93i8GRKrs8xnX9rv6PnN462OCA?type=png)](https://mermaid.live/edit#pako:eNpVjj0LwjAQhv9KuCmBdvFjySCoHXXRNcuRXG2xSSQmFCn9754fS9_lXh4ejncCGx2BhnaIo-0wZXG6mCA4K7lXoq6Fi2PguxNreViCjTyqv7vgW9koqMBT8tg7fj59LAO5I08GNFeH6W7AhJk9LDleX8GCzqlQBeXhMFPT4y2hB93i8GRKrs8xnX9rv6PnN462OCA)

## `BC-list-note-neighbour-field`

Normally, only the parent/child relationships are added. But you can also add edges based on the _neighbours_ of each list item. This is useful for adding sibling/next/prev relationships.

```yaml
BC-list-note-neighbour-field: <field>
```

Where `<field>` is one of your Breadcrumbs fields.

In the first List Note example above, this would add edges from `B` to `D`.

[![](https://mermaid.ink/img/pako:eNpVz7EOgjAQBuBXaW4qCQyCLh1MVEZ00LVLQw9tpK0pR9AQ3t0iLtxyly-Xy_0j1F4jCGhaP9QPFYhVV-lYrA2vTEfs4gkTlmVM-8HFvmc5P6yh4Mc1bPkpWY7kK9_x8u_F7A7ftDikYDFYZXR8ZZxXJNADLUoQcdQqPCVIN8U91ZO_fVwNgkKPKfQvrQhLo-5BWRCNaruoqA35cF6y_SJOX71eRAE?type=png)](https://mermaid.live/edit#pako:eNpVz7EOgjAQBuBXaW4qCQyCLh1MVEZ00LVLQw9tpK0pR9AQ3t0iLtxyly-Xy_0j1F4jCGhaP9QPFYhVV-lYrA2vTEfs4gkTlmVM-8HFvmc5P6yh4Mc1bPkpWY7kK9_x8u_F7A7ftDikYDFYZXR8ZZxXJNADLUoQcdQqPCVIN8U91ZO_fVwNgkKPKfQvrQhLo-5BWRCNaruoqA35cF6y_SJOX71eRAE)

## Settings

- **Default Neighbour Field**: Choose a default field to use for the neighbour relationships. This is useful if you have a _lot_ of list notes, and don't want to add the `BC-list-note-neighbour-field` to each one.
