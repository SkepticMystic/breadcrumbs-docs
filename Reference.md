Various theoretical concepts used across Breadcrumbs

## Node Attributes

Each node in the Breadcrumbs graph has the following attributes:

- `resolved`: Whether the note is resolved or not
- `aliases`: Any aliases of the note, used for display purposes

## Edge Attributes

Edges in the Breadcrumbs graph have a few attributes to them:

- `field`: Which [[Edge Fields|edge field]] was used
- `explicit`: Whether the edge is [[Explicit Edge Builders|explicit]] or [[Implied Edge Builders|implied]]
- `source`: If the edge is explicit, which [[Explicit Edge Builders|edge builder]] added it
- `implied_kind`: If the edge is implied, which [[Implied Edge Builders|implied rule]] added it
- `round`: If the edge is implied, which [[Implied Relation Rounds|round]] was it added in

## Edge Sorters

Various Breadcrumbs functions let you sort a list of (potentially nested) edges. The available fields to sort by include:

- `basename`: sorts by the basename of the target note.
- `path`: sorts by the full path of the target note.
- `field`: sorts by the [[Edge Fields|field]] of the edge.
- `explicit`: sorts by the explicitness of the edge.
  - Uses `source` as a tiebreaker for [[Explicit Edge Builders|explicit]] edges, and `implied_kind` for [[Implied Edge Builders|implied]] edges.

There are more complex sort fields as well:

- `neighbour-field:<field>` sort by the _path_ of the first neighbour of the note in the given `<field>`.
  - Useful for sorting by the `next` neighbour.
