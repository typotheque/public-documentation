# Peter's preferred way to draw `Lcaron`, `lcaron`

## Shape
At Typotheque, we name the caron required for Lcaron, `caron.slovak`. Instead of using the shape of curly quote, I prefer to use a simple shape. Think of it as a right side of the regular caron.

<img width="1199" height="227" alt="image" src="https://github.com/user-attachments/assets/c3084fa8-75d6-4524-8415-881affff0503" />


## Spacing
Spacing of lcaron should not disturb overall spacing of letters, and it should look as close as possible as if spelling the word with regular `l`

<img width="1467" height="218" alt="image" src="https://github.com/user-attachments/assets/df903a75-de47-4ffb-85bb-307780a9d883" />

## Position
Instead of aligning it with the top of the letter, it is important to think of other possible diacritics. A good test is a word `Sporiteľňa` (Bank in Slovak). When the `caron.slovak` is aligned with the top of the L, it will sit too low. I usually make it exceed the L by 30-50%, but not too high, so it doesn't start looking like `Lacute`.

<img width="1531" height="132" alt="image" src="https://github.com/user-attachments/assets/8682bb43-44c3-44ed-9cb0-5cb42ae66e38" />

## Collision prevention
In Slab serif fonts it is not easy to prevent collision with following letters with ascenders. Slovak corpus shows only one such letter `k`, and usually it is important to kern lcaron-k to avoid the collision. 

<img width="1349" height="170" alt="image" src="https://github.com/user-attachments/assets/271fb964-a519-4af8-a853-7ebffc037364" />

This may create a rather large white space between lcaron and k.

<img width="1362" height="173" alt="image" src="https://github.com/user-attachments/assets/05c5ae68-d744-4fc6-a5ce-0de0aa5e78b2" />

Alternative possibility would be to create a contextual version of `k.calt` which is used when following `lcaron`. Use this approach with caution, as it may not work in all styles. [November Slab](https://www.typotheque.com/fonts/november-slab) is using this approach, and a few other fonts.

<img width="1350" height="178" alt="image" src="https://github.com/user-attachments/assets/1ab98c6f-684e-467a-9363-32a432b88cc8" />

You will need to define `calt` feature:
`sub lcaron k' by k.calt;`

