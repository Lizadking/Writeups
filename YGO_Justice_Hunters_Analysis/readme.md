
# Hot Singles in your Pack: An Analysis of Yu-Gi-Oh Card Probabilities Using Binomial Probability

## 

Recently I've made the grave mistake of getting into playing Yu-Gi-Oh. And it all started from buying a simple box of one of the latest sets of 2025 *Justice Hunters*, and I wanted to build a deck using the set's newest Arcetypes, K9 but these cards aren't always guarenteed. The rates as specified by Konami for this archetype are typically *Secret Rares*. This leads to the issue, do I spend my time buying packs opening them and seeing if I pull more K9 cards for my deck,
or do I buy singles? How many packs would I have to open to get a specific card vs just buying it online?

## The Hunters for Justice (And some Yummy Cats)

The main set of discussion is *Justice Hunters* released by Konami in the US on 8/1/2025 and features over 60 cards with 40 Monster cards in total. Featuring the newest archetypes "Dracotail","K9" and the "Yummy"
The following rarity stats are given as below:

![K9_set_information](./assets/unnamed.png)

As we can see with ten Ultra Rares (UR) and ten Super Rares (SR) we are working with about twenty cards we are inerested at that can be considered "above rare" since the core K9 cards we care about in this set (K9-17 "Ripper" for example) is printed only at Super and Collector's rare rarities.

In addition we know a bit more about each booster pack we buy, as the first six cards of any pack will be printed at Rare rarity and only the seventh card in the pack will be printed at above Rare in rarity. This just makes the hunt for the cards we want even harder

## A Case for K9: What are we trying to do here?

Assuming an equally randomly distributed pack, if the initial six cards are guaranteed to be at rare rarity with the final card being at or above Super Rare rarity, what are the odds of being able to pull a specific card at a given rarity roughly estimate how many packs it would take to reasonably pull that specific card and doing a cost benefit analysis between pulling more packs or buying a single?

## Catching a Scent: Choosing a Method
In order to evaluate this question I needed some way to model the situation. I open a pack, either I pull the card I've been looking for or I do not. It is a 
binary success or failure. In addition I needed a way to simulate opening repeated packs and once again either I succeed or fail. These are the perfect conditions that met using what is called a **Binomial Distribution**. 

A Binomial Distribution is the probability distribution of the number of successes in a sequence of independent events that can only have the chances of passing or failing. Essentially, it's the disribution of the amount of successes given a fixed amount of trials and can be represented by the formula:
$`f(k,n,p) = \Pr(X = k) = \binom{n}{k}p^k(1-p)^{n-k}`$

## How Rare is a Rare? 

Okay there are a lot of rarities in Yu-Gi-Oh, like a lot a lot, as in well over 40+ rarities. We can spend a lot of time discussing and talking about rarities that will simply not happen here ( But you can go [here](https://www.yugiohcardguide.com/guide_to_card_rarity.html) to read about all the rarities and the unique vartients and even some US only printings as well as [watch this](https://www.youtube.com/watch?v=vZ_jgMZGHoU) for additional explanations) 
And for this write-up, they don't matter. 

We just need to understand a rarity is simply a card that is printed at less often than other cards which makes them rare. But the issue is the information online about the rates these cards are printed at is inconsitent no one online seems to be able to coroborate each other's numbeers (sometimes you will have to scour Byzinte era fourms for some guy's "trust me bro" ratios) and the numbers are at best estimates by fans. 

But for our concerns there are only five rarities that are of any note as this set only has five rarities and they are and at the ratios (cards/booster pack):
- Rare (1:1)
- Super Rare (1:5)
- Ultra Rare (1:6)
- Collector's Rare (1:84)
- Starlight Rare (1:576)

### Sources 
https://en.wikipedia.org/wiki/Binomial_distribution