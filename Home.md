Welcome to the Breadcrumbs docs 🍞 Here you can find more detailed explanations of the various functions of the Obsidian [Breadcrumbs plugin](https://github.com/SkepticMystic/breadcrumbs).

> [!INFO]
> Breadcrumbs lets you add _typed links_ to your notes. You supply the structure, Breadcrumbs helps you leverage it.

## Quick Start

To quickly see one way Breadcrumbs works, you can do the following:

- Install & enable Breadcrumbs
- Open a new note
- Add `up: [[note]]` as a metadata Properties field
	- [Dataview](http://blacksmithgu.github.io/obsidian-dataview/) inline fields work too `up:: [[note]]`
- Run the "**Breadcrumbs: Rebuild Graph**" command to refresh the Breadcrumbs graph
- Then run the "**Breadcrumbs: Open Matrix View**" command
	- See how the Matrix View shows a link pointing "_up_" to `[[note]]`

In the terminology of Breadcrumbs, you've just used the "[[Typed Links|typed-link]]" edge builder to add an [[Explicit Edge Builders|explicit edge]] from one note to another, using the `up` [[Edge Fields|edge field]].

## Overview

- Setup your [[Edge Fields]]
	- Breadcrumbs comes with 5 generic edge fields, but you can customise these as needed
- Add structure to your notes using the various [[Explicit Edge Builders|Explicit Edge Builders]]
	- Some builders are manual, while others can automatically use your existing structure
- Fill in the gaps with the [[Implied Edge Builders|Implied Edge Builders]]
	- Breadcrumbs can _infer_ more complex relationships from the initial ones added by the Explicit Edge Builder
	- You have full control over the rules for adding implied edges
- Use the [[Views|Views]] to see your fields in action
- Try out the [[Commands|Commands]] to do other useful stuff
