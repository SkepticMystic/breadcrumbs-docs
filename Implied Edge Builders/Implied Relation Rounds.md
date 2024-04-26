Not only can you enable/disable each kind of implied relation, you can change how many _rounds_ to go through to detect them. This is useful to add implied relations _based on other implied relations_.

- Setting rounds to `0` disables that kind.
- Setting it to `1` will add that kind of implied relation, only considering _explicit_ edges.
- Setting it to `2` will add that kind of implied relation again, considering _explicit_ edges and _previously added_ implied edges. And so on...

## Example

Say you have the following explicit edges (two notes pointing `up` to their parent):

```mermaid
flowchart LR
	1(A) -- up --> 2(Parent)
	3(B) -- up --> 2
```

If you have the [[Transitive Implied Relations#Parents Child is Sibling|Parent's Child is Sibling]] implied relation enabled, you may expect `A` and `B` to be marked as siblings, since they share the same parent. But in this example, they won't since there isn't a chain of `[up, down]` between the two. Instead, they both point `up`. To achieve the same effect, we can use the [[Transitive Implied Relations#Opposite Direction|opposite direction]] implied relation to add the `down` edges we need:

```mermaid
flowchart LR
	1(A) -- up --> 2(Parent)
	3(B) -- up --> 2
	2 -. down .-> 1
	2 -. down .-> 3
```

Now there is a chain of `[up, down]` between `A` and `B` (`A -up-> Parent -down-> B)`. But, because the `down` edge is implied, we have to increase the _rounds_ of the Parents' Child is Sibling relation to `2` to detect it. If it was only on `1`, then it wouldn't consider the implied edges added by the Opposite Direction relation.

```mermaid
graph LR
	1(A) -- up --> 2(Parent)
	3(B) -- up --> 2
	2 -- down --> 1
	2 -- down --> 3
	1 -. same .-> 3
```

> [!TIP]
> You can think of increasing the rounds as making all _previous_ implied relations **explicit**. So, in the above example, increasing the rounds of the Parents' Child is Sibling relation to `2` would make the `down` edge between `A` and `B` explicit (because they were added in round `1`), and then detect the sibling relationship.
