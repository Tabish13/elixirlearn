# Cards

**Pattern Matching: Pattern matching is widely used in elixir for assign a variable i.e. return a value to variable on performing some operation**

## Example
Let's return a list of cards from the deck as specified the hand by the value i.e. suppose we have 10 cards an we need 4 cards so we should get 4 cards return from the list of cards passed.

```
def deal(deck, hand)do
    Enum.split(deck, hand)
end
```

Explanation
```
{deal, remaining_cards} = deal(["Ace of Spades", "Two of Spades", "Three of Spaded", "Four of Spades" , "Five of Spades"], 2)
```

Output of deal function is:
```
{
  ["Ace of Spades", "Two of Spades"],
  [..]
}
```

The syntax 
```
{deal, remaining_cards} = ...
```
will assign the tuple first element to deal variable and the remaining cards are stored in second variable on the left side. This is possible due to pattern matching of elixir 

It compares the left side with right side i.e.

```
Left side:
{deal, remaining_cards} 

Right side:
{
  ["Ace of Spades", "Two of Spades"],
  [..]
}

So deal is list of the card present on the right side and the remaining_cards is the second list on the right side.
```
i.e if we print deal it will output 
```
["Ace of Spades", "Two of Spades"]
```

## To Run sample code run the below scripts:
```
iex -S mix

cards = Cards.create_deck
shuffled_cards = Cards.shuffle(cards)
{deal, remaining_cards} = Cards.deal(shuffled_cards, 5)
```
To check the deal variable print the deal
```
deal
```
