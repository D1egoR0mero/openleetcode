### Approach

Scan the array once while tracking the lowest price seen so far. For each day, the best profit from selling on that day is the current price minus that minimum, so update the maximum profit whenever the current day's profit is larger. If prices only fall, the maximum profit stays at `0`.

### Implementation

```python
from typing import List


class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        min_price = prices[0]
        max_profit = 0

        for price in prices[1:]:
            if price < min_price:
                min_price = price

            profit = price - min_price
            if profit > max_profit:
                max_profit = profit

        return max_profit
```

### Complexity Analysis

* Time complexity: **O(n)**.
* Space complexity: **O(1)**.
