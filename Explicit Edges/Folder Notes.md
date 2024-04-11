_Folder Notes_ allow you to leverage your existing folder structure. You can turn a note into a folder note by adding the following to your frontmatter:

```yaml
BC-folder-note-field: <field>
```

Where `<field>` is one of your Breadcrumbs fields. Breadcrumbs will add edges from the current note to all _other_ notes in the same folder, using the field you specify.

[![](https://mermaid.ink/img/pako:eNo1jjELwkAMhf9KyCAWWkTdbhCUrk463hKa1B727iReqVL63z2VviXvJeHxTdhEFjTY9nFsOtIE19oGyNqu29iz6MYFllcBVQUcx5DnAXbL7VjACvZLOhVYohf15Dh3Tt8ii6kTLxZNtkx6t2jDnP9oSPHyDg2apIOUODyYktSObkoeTUv9M2-FXYp6_kP-WOcP2Ns5uQ?type=png)](https://mermaid.live/edit#pako:eNo1jjELwkAMhf9KyCAWWkTdbhCUrk463hKa1B727iReqVL63z2VviXvJeHxTdhEFjTY9nFsOtIE19oGyNqu29iz6MYFllcBVQUcx5DnAXbL7VjACvZLOhVYohf15Dh3Tt8ii6kTLxZNtkx6t2jDnP9oSPHyDg2apIOUODyYktSObkoeTUv9M2-FXYp6_kP-WOcP2Ns5uQ)

## `BC-folder-note-recurse`

By default, Breadcrumbs will only add edges to notes in the _immediate_ folder. If you want to add edges to notes in _all_ subfolders, you can add the `BC-folder-note-recurse` field to the frontmatter of the folder note.

```yaml
BC-folder-note-recurse: true
```

[![](https://mermaid.ink/img/pako:eNo1j08LwjAMxb9KyUEcbIh_Tj0Ijl096bGXuGSuuLbStUwZ--526nLJ-yWB9zJC7YhBQtO5oW7RB3GtlBWptuvGdcR-oy3xKxNFIcgNNvWj2C27UyZWYr9QOdNhoT7e_gozyMGwN6gpeY2zgYLQsmEFMklC_1Cg7JTuMAZ3edsaZPCRc4hPwsCVxrtHA7LBrk9TJh2cP__Cf3-YPpJbQaU?type=png)](https://mermaid.live/edit#pako:eNo1j08LwjAMxb9KyUEcbIh_Tj0Ijl096bGXuGSuuLbStUwZ--526nLJ-yWB9zJC7YhBQtO5oW7RB3GtlBWptuvGdcR-oy3xKxNFIcgNNvWj2C27UyZWYr9QOdNhoT7e_gozyMGwN6gpeY2zgYLQsmEFMklC_1Cg7JTuMAZ3edsaZPCRc4hPwsCVxrtHA7LBrk9TJh2cP__Cf3-YPpJbQaU)

> [!IMPORTANT]
> This doesn't create _nested_ edges. It effectively flattens your folder structure into one level, so notes in subfolders will still be added as children of the _top-level_ folder note, not as children of the notes in the subfolders.
