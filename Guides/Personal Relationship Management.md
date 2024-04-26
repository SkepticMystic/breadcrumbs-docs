Similar to [Monica](https://github.com/monicahq/monica), Breadcrumbs can be used to manage personal relationships. Vanilla Obsidian can easily handle alot of the functionality of a personal CRM, but Breadcrumbs is particularly helpful when it comes to noting relationships between people, and inferring more complex relations from those.

## Steps

### 1. Edge Fields

We'll start off with some basic, immediate relationships. Add these under your [[Edge Fields]] in `Settings > Edge Fields`:

- `parent`
- `sibling`
- `child`
- `spouse`
- `friend`

![[Personal Relationship Management EdgeFieldSettings.png]]

### 2. Add Some Typed-links

Next, add some notes for different people, and link them up using these new fields. For example, in the note about yourself, you can add the following (using the [[Typed Links|typed-link edge builder]]):

**Me.md**

```md
---
parent: "[[Father]]"
---

%% Dataview inline fields work, too %%

parent:: [[Mother]]
```

[[Rebuild Graph|Rebuild the graph]], check the [[Matrix View]], and confirm that the note points to your parents.

### 3. Implied Relationships

Using the [[Implied Edge Builders]], we can craft custom relationships for Breadcrumbs to add automatically, based on the simpler ones added previously. For example, we could add the following:

- `[parent] <- child`: You are your parent's child

![[transitive (parent) <- child.png]]

- `[parent, child] -> sibling`: Your parent's other children are your siblings

![[transitive (parent, child) -> sibling.png]]

- `[spouse, sibling] -> sibling-in-law`: Your spouse's sibling is your sibling-in-law

![[transitive (spouse, sibling) -> sibling-in-law.png]]

> [!NOTE]
> You can use any combination of fields in the implied rules. But the closing field also has to be in your [[Edge Fields]], so remember to add them there first.

After adding some implied relations, [[Rebuild Graph|rebuild the graph]], and check the [[Matrix View]] again. You should see some extra relationships filled in, without you having to explicitly define them!

### 4. Visualising

After you've expanded your people-graph, you can visualise it using a [[Codeblocks|mermaid codeblock]]. The following shows _all_ relationships from the perspective of the current note (resulting in a potentially huge graph ⚠️):

```
type: mermaid
merge-fields: true
show-attributes: [field]
```

## Extras/Advanced Usage

### More Fields

You can model many other types of relationships, for example:

- Work relationships: `manager`, `manages`, `colleague`
- School relationships: `teacher`, `student`, `class-mate`
