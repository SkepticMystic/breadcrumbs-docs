Not only can you enable/disable each kind of implied relation, you can change how many _rounds_ to go through to detect them. This is useful to add implied relations _based on other implied relations_.

- Setting rounds to `0` disables that kind.
- Setting it to `1` will add that kind of implied relation, only considering _explicit_ edges.
- Setting it to `2` will add that kind of implied relation again, considering _explicit_ edges and _previously added_ implied edges. And so on...

## Example

Say you have the following explicit edges (two notes pointing `up` to their parent):

[![](https://mermaid.ink/img/pako:eNpVTrEKwjAU_JXwphbaQd0yCIqjBdE1yyN5tcEmKc8XREr_3WgnbziOu-O4GWxyBBr6Mb3sgCzqfDVRFWyqQ63aVuWp8F5tqwsyRanXdFcd_1JoIBAH9K6Mzd-OARkokAFdpEN-GDBxKT3Mkm7vaEELZ2ogTw6FTh7vjAF0j-OzuOS8JO7Wd7-TywfrETSq?type=png)](https://mermaid.live/edit#pako:eNpVTrEKwjAU_JXwphbaQd0yCIqjBdE1yyN5tcEmKc8XREr_3WgnbziOu-O4GWxyBBr6Mb3sgCzqfDVRFWyqQ63aVuWp8F5tqwsyRanXdFcd_1JoIBAH9K6Mzd-OARkokAFdpEN-GDBxKT3Mkm7vaEELZ2ogTw6FTh7vjAF0j-OzuOS8JO7Wd7-TywfrETSq)

If you have the [[Transitive Implied Relations#Parents Child is Sibling|Parent's Child is Sibling]] implied relation enabled, you may expect `A` and `B` to be marked as siblings, since they share the same parent. But in this example, they won't since there isn't a chain of `[up, down]` between the two. Instead, they both point `up`. To achieve the same effect, we can use the [[Other Implied Relations#Opposite Direction|Opposite Direction]] implied relation to add the `down` edges we need:

[![](https://mermaid.ink/img/pako:eNptj8EKwjAQRH9l2VMLbaHtLQdB8agges1laba22CQlJhQp_XejOQnOYRneDCyzYmcVo8B-sks3kPNwukoDUXW2z6EsIczx7qDJLuTY-DylbXb4SRNtoKxA2cVAFWH9D7ZYoGanaVTx7fqpSPQDa5YoolXkHhKl2WKPgre3l-lQeBe4wDAr8nwc6e5Io-hpekbKavTWndOO75ztDatEPl4?type=png)](https://mermaid.live/edit#pako:eNptj8EKwjAQRH9l2VMLbaHtLQdB8agges1laba22CQlJhQp_XejOQnOYRneDCyzYmcVo8B-sks3kPNwukoDUXW2z6EsIczx7qDJLuTY-DylbXb4SRNtoKxA2cVAFWH9D7ZYoGanaVTx7fqpSPQDa5YoolXkHhKl2WKPgre3l-lQeBe4wDAr8nwc6e5Io-hpekbKavTWndOO75ztDatEPl4)

Now there is a chain of `[up, down]` between `A` and `B` (`A -up-> Parent -down-> B)`. But, because the `down` edge is implied, we have to increase the _rounds_ of the Parents' Child is Sibling relation to `2` to detect it. If it was only on `1`, then it wouldn't consider the implied edges added by the Opposite Direction relation.

[![](https://mermaid.ink/img/pako:eNptjzELgzAQhf_KcZOCCuqWodDSsYXSrlkOc1bBJBITShH_e6N2KfSG4_je43hvxsYqRoFPR2MHl7s0EKdMjinkOYQx7gNUyY0cG5_uap2cftSdVitS9mU2WP6D9fc75AVMpBmKFWKGmp2mXsUc82qR6DvWLFHEU3FLYfASpVmilYK3j7dpUHgXOMMwKvJ87ik20ChaGqZIWfXeuuvebau4fABhA0Kt?type=png)](https://mermaid.live/edit#pako:eNptjzELgzAQhf_KcZOCCuqWodDSsYXSrlkOc1bBJBITShH_e6N2KfSG4_je43hvxsYqRoFPR2MHl7s0EKdMjinkOYQx7gNUyY0cG5_uap2cftSdVitS9mU2WP6D9fc75AVMpBmKFWKGmp2mXsUc82qR6DvWLFHEU3FLYfASpVmilYK3j7dpUHgXOMMwKvJ87ik20ChaGqZIWfXeuuvebau4fABhA0Kt)

You can think of increasing the rounds as making all _previous_ implied relations **explicit**. So, in the above example, increasing the rounds of the Parents' Child is Sibling relation to `2` would make the `down` edge between `A` and `B` explicit (because they were added in round `1`), and then detect the sibling relationship.
