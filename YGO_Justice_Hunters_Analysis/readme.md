
# Hot Singles in your Pack: An Analysis of Yu-Gi-Oh Card Probabilities Using Binomial Probability
![Justice Hunters Set](./assets/OIP-1938437927.jpg)
## 

Recently I've made the grave mistake of getting into playing Yu-Gi-Oh. And it all started from buying a simple box of one of the latest sets of 2025 *Justice Hunters*, and I wanted to build a deck using the set's newest Arctypes, K9 a really cool detective themed archtype but these cards aren't always guarenteed. The rates as specified by Konami for this archetype are typically *Secret Rares*. This leads to the issue, do I spend my time buying packs opening them and seeing if I pull more K9 cards for my deck,
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
binary success or failure.  These packs are also independent of each other[^1]. And the probability of getting a card above Rare in rarity doesn't change. These are the perfect conditions that met using what is called a **Binomial Distribution**. 

A Binomial Distribution is the probability distribution of the number of successes in a sequence of independent events that can only have the chances of passing or failing. Essentially, it's the disribution of the amount of successes given a fixed amount of trials and can be represented by the formula:


$`f(k,n,p) = \Pr(X = k) = \binom{n}{k}p^k(1-p)^{n-k}`$

for $`{{k{{=}} 0, 1, 2, ..., n}}`$

Using n as the number of packs we open and k being the number of succesess we can evaluate the probability of pulling a specifc card at a specific rarity above Rare

But the problem now is to calculate the probability in general, as well as specify what above rare really means 

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

## Following the Trail : Calculating Probabilities 
### Assumptions 

-  Assume Konami did not short print any cards to effect the rarity distribution (let’s act like they’re nice for once)
-  Each Pack contains unique cards, there are no duplicates 
-  Card 7 is guaranteed to be above rare in rarity 
- Each card in the set of possible cards has an equal likelihood of being in a pack (we do not know how Konami prints cards for each pack) 
- All rarities above rare (Super, Ultra, Starlight and collectors) will be considered under the same group of "above rare rarity" (There are no unique cards printed above Ultra rare, only variants)

### Case One: Trivial Case
The most trivial probability calculation is simply finding the odds of pulling a specific card at above rare odds which is the following formula 

$`P(x) = \frac{1}{20}`$

Where 1/20 is the odds of pulling from one of the twenty above Rare rarity cards 
This is incredibly boring as we already know this via the set information Konami gave but it's a usueful baseline
### Case Two: Probability with a given rarity
Since we are looking for cards that appear at a certain rarity the probability can be found using the above given ratios of rarities with:
$`P(x) = \frac{1}{20}R`$

Where R is the given rarity of the card (Super, Ultra,Collector's,etc)

So let's use this to map out the probability distribution for a specific card I want. Let's use K9-17 "Ripper" at Super Rare rarity for the rest of these calculations

![K9_17](./assets/330px-K917Ripper-JUSH-EN-SR-1E.png)


[^1]: This only applies to individual packs, not boxes as boxes have fixed rates. You will always pull at least two Secret Rares from a box. But let's ignore them for this line of questioning. 
### Sources 
https://en.wikipedia.org/wiki/Binomial_distribution
https://www.yugiohcardguide.com/guide_to_card_rarity.html
https://www.db.yugioh-card.com/yugiohdb/
