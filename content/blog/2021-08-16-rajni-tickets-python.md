<!-- title: ChangeMaster Challenge  -->

## Can you give Change?

The new "Master" movie has just been released! There are a lot of people at the cinema box office standing in a huge line. Each of them has a single `100`, `50` or `25` rupee note. A "Master" ticket costs `25 rupees`.

The clerk at the box office is Ramesh. He wants to sell a ticket to every single person in this line. 

Can Ramesh sell a ticket to every person and give change if he initially has no money and sells the tickets strictly in the order people queue?

Return `"YES"`, if Ramesh can sell a ticket to every person and give change with the bills he has at hand at that moment. Otherwise return `"NO"`.

Write a Python function **`tickets_plus`** that accepts a list of numbers as its argument and returns "YES" or "NO". 

**NOTE**: As part of settling the change, Ramesh gives away the higher denomination notes first. For e.g. if change of 75 has to be given, Ramesh will give out 50 + 25, even though he might have seven 10 rupee notes and a 5 rupee note.  


### Examples:

```python
tickets([25, 25, 50]) # => YES 
tickets([25, 100]) # => NO
# Ramesh will not have enough money to  
# give change to 100 rupees
tickets([25, 25, 50, 50, 100]) # => NO
# Ramesh will not have the right bills to
# give 75 rupees of change (you can't make 
# two bills of 25 from one of 50)
```

## Variation 2 

The next day, it is anticipated that people may join the queue with 30 rupees in hand.  In that case, the person only has three 10 rupee notes.**  In anticipation of this, to start with, Ramesh decides to start with 5 rupee bills (exactly 9 in number). Modify the logic to accommodate this situation. 

### Examples:

```python
tickets([25, 30, 50]) # => YES 
# Ramesh has a 5 already, so he can take 30, and return 5 
tickets([30, 30, 30, 30, 30, 30, 30, 30, 30, 30]) # => NO 
# Ramesh runs out of 5 rupee notes
tickets([30, 50]) $ => YES
# Ramesh makes 25 out of two 10 rupee notes and one 5 rupee note
```


## Variation 3 

Refactor your logic for Variation 2 so that it can also very easily be adapted for other types of denomination notes that might come into circulation in the ticket queue. Ramesh might also decide to have an initial cashbox containing not just 5 rupee notes, but also other denominations as well. 

