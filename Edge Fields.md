---
aliases:
  - edge fields
  - field
---

The starting point of Breadcrumbs is _fields_, which let you add _types_ to your links. For example, the `[[Father]]` note could have a `child` field pointing to `[[Me]]`, and `[[Me]]` could have a `parent` field pointing to `[[Mother]]`:

**Father.md**

```md
---
child: "[[Me]]"
---
```

**Me.md**

```md
---
parent: "[[Mother]]"
---

%% Works with Dataview inline fields, too %%

parent:: [[Mother]]
```

This would result in the following [[Reference#Graph|graph]]:

```mermaid
flowchart LR
	1(Father) -- child --> 2(Me)
	2 -- parent --> 3(Mother)
```

---

By default, there will be 5 starting fields: `up`, `same`, `down`, `next`, and `prev`, representing 5 different directions. These can take you quite far, and you may be happy using just these fields, but you can customise them further. To get started, you need to tell Breadcrumbs which other fields you intend to use to "type" your links. This can be done under `Settings > Edge Fields`:

![[Edge Field Settings.png]]

For example, you can [[Personal Relationship Management|model personal relationships]] using fields like `parent`, `child`, and `sibling`. Or you can create a [[Layered Daily Notes|layered system of daily notes]] using fields like `day`, `month`, and `year`.
