<!-- title: ChangeMaster Challenge  -->

## Can you give Change?

The new "Master" movie has just been released! There are a lot of people at the cinema box office standing in a huge line. Each of them has a single `100`, `50` or `25` rupee note. A "Master" ticket costs `25 rupees`.

The clerk at the box office is Ramesh. He wants to sell a ticket to every single person in this line. 

Can Ramesh sell a ticket to every person and give change if he initially has no money and sells the tickets strictly in the order people queue?

Return `1`, if Ramesh can sell a ticket to every person and give change with the bills he has at hand at that moment. Otherwise return `0`.

**NOTE**: As part of settling the change, Ramesh gives away 50 rupee notes first, if there should be any. 

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

Assume people in line have 10 rupee notes (for e.g. 30 is 3 times 10). To start with, assume Ramesh carries with him 5 rupee bills (9 in number). Modify the logic to accommodate this situation. 

### Use as deemed fit  
```python
import copy
 
def make_change(options, cashbox): 
    
    for combo in options:
        for denom in combo: 
            if denom not in cashbox or \
                combo[denom] > cashbox[denom]:
                    break
        else:
            return combo
        
    return None
 
 
''' 
var generate25 = [ {25:1}, {5:1, 10:2}, {5:3, 10:1}, {5:5}];
 
var generate75 = [ {25:1, 50:1}, {25:3}, {5:1, 10:7}, 
    {5:1, 10:2, 25:2}, {5:1, 10:2, 50:1}, {5:3, 10:1, 25:2}, 
    {5:3, 10:1, 50:1}, {10:5, 25:1}, {5:15}... 22 combinations ];
 
'''
 
def maxkey(obj): 
    return max(list(obj.keys()))
 
def generate(money, coins): 
    table = {}    
    
    for i in range(1, money+1): 
        row = []
        for c in coins: 
            if c < i: 
                subs = table[i - c]
                for s in subs: 
                    sub = copy.deepcopy(s)
                    max = maxkey(sub)
                    if c >= max: 
                        sub[c] = sub[c] + 1 if c in sub else 1 
                        row.append(sub)
                # end of subs for loop
            elif c == i:
                combo = {}
                combo[c] = 1
                row.append(combo)
        # end of coins loop 
        table[i] = row
        #print("table", table[i])
    # end of money loop 
    return table[money]
```


## Variation 3 
http://j.mp/waysToMakeA100 can be explored further for refining makeChange module  
 
SPOILER ALERT!   
http://j.mp/numberPartitions  
http://j.mp/kenOnoNumberPartitions  




