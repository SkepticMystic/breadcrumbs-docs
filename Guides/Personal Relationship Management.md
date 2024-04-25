Similar to [Monica](https://github.com/monicahq/monica), Breadcrumbs can be used to manage personal relationships. Vanilla Obsidian can easily handle alot of the functionality of a personal CRM, but Breadcrumbs is particularly helpful when it comes to noting relationships between people, and inferring more complex relations from those.

## Setup

We'll start off with some basic, immediate relationships. Add these under your [[Edge Fields]]:

- `parent`
- `sibling`
- `child`
- `spouse`
- `friend`

Next, add some notes for different people, and link them up using these fields. For example, in the note about yourself, you can add the following (using the [[Typed Links|typed-link edge builder]]):

**Me.md**

```md
---
parent: "[[Father]]"
---

parent:: [[Mother]]
```

Refresh the graph, check the [[Matrix View]], and confirm that the note points to your parents.

## Implied Relationships

Using the [[Implied Edge Builders]], we can craft custom relationships for Breadcrumbs to add automatically, based on the simpler ones added previously. For example, we could add the following:

- `[parent] <- child`: You are your parent's child
- `[parent, child] -> sibling`: Your parent's other children are your siblings
- `[spouse, sibling] -> sibling-in-law`: Your spouse's sibling is your sibling-in-law

> [!NOTE]
> You can use any combination of fields in the implied rules. But the closing field also has to be in your [[Edge Fields]], so remember to add them there first.

After adding some implied relations, [[Rebuild Graph|rebuild the graph]], and check the [[Matrix View]] again. You should see some extra relationships filled in, without you having to explicitly define them!

## Visualising

After you've expanded your people-graph, you can visualise it using a [[Codeblocks|mermaid codeblock]]. The following shows _all_ relationships (resulting in a potentially huge graph)

```
type: mermaid
merge-fields: true
show-attributes: field
```
