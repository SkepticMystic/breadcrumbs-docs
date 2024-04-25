🍞 **Breadcrumbs** has a powerful new feature: _custom_ implied relationships!

This fully generalises the existing implied relation system (e.g. "Same Parent is Sibling"). The most powerful part is that you can use fields from _different hierarchies_! For example, if you have one hierarchy with a `spouse` field, one hierarchy with `sibling`, and one with `sibling-in-law`, you can create a chain of `[spouse, sibling] -> sibling-in-law`. In other words, your spouse's sibling is your sibling-in-law.

You can add some under Settings > Custom Implied Relations. Here's the relevant section in the docs: <https://github.com/SkepticMystic/breadcrumbs#transitive-implied-relations>. The feature is currently only available in the V4 beta, accessible with the BRAT plugin.

Let me know if it all makes sense, give it a try, and please share any feedback 🙂

---

Message Link: [Discord](https://discord.com/channels/686053708261228577/855181471643861002/1220298808727044257)

next:: [[Announcement 2024-04-01]]
