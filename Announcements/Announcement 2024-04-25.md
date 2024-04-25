## Breadcrumbs 🍞

⚠️ Two important changes are now available in beta:

1. Hierarchies are Directions are no more. There are now just fields, and groups of fields.
2. **BREAKING**: Breadcrumbs codeblocks are now parsed as YAML.

The first change is non-breaking, but does represent a different way of thinking about Breadcrumbs. You can read more here: <https://publish.obsidian.md/breadcrumbs-docs>. The **Quick-Start** and **Overview** on the Home page will guide you. But to summarise:

- The abstraction of Directions and Hierarchies is gone. Instead, there are now only [Fields](https://publish.obsidian.md/breadcrumbs-docs/Edge+Fields), and [Field Groups](https://publish.obsidian.md/breadcrumbs-docs/Field+Groups). You can _choose_ to represent the directions as groups, but no longer **have to**.
- A migration script will translate your old settings to the new version. The script will use Field Groups to replicate your existing setup, so everything should behave as before on first-load. I recommend scrolling through the BC settings to get a feel.
- The old way of specifying implied relations now uses a system of [transitive chains](https://publish.obsidian.md/breadcrumbs-docs/Implied+Edge+Builders/Transitive+Implied+Relations), which provides a **superset** of functionality - everything previous is possible, and more.

On the second point, _most_ codeblock fields will behave as before, because they happened to be valid YAML. But the following need changing:

- `fields` is now a `string[]`, instead of a comma-separated list
- Same with `field-groups`, and `show-attributes`
- `depth` is now a `[number, number]`, instead of a `"number-number"` string

See the [codeblock docs](https://publish.obsidian.md/breadcrumbs-docs/Views/Codeblocks) for more info. You'll get detailed error messages in each codeblock when it tries to render.

---

As always, thank you to everyone who suggested/tested these changes. In particular, Lemons, Daniel, and Abi this time :green_heart:
