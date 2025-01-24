15/10/24 11:51
Tags: [[Programmering]]
___

# BEST TIME TO BUY AND SELL

akkurat som [[TWO SUM]]. bare anna condition

## forsøk 1
```c++
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int profit = 0;
        for (int i = 0; i < prices.size()-1; i++) {
            for (int j = i + 1; j < prices.size(); j++) {
                if (prices[j] - prices[i] > profit) {
                    profit = prices[j] - prices[i];
                }
            }
        }
        return profit;
    }
};

```

er for treig??

## forsøk 2
```c++
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int start = prices[0];
        int end = 0;
        for (int i = 1; i < prices.size()-1; i++) {
            if (start > prices[i]) {
                start = prices[i];
                end = 0;
            }
            if (end < prices[i+1]) end = prices[i+1];
        }
        if (end - start > 0) return end-start;
        else return 0;
    }
};

```

## forsøk 3
mye enklere enn trodde:

```c++
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int start = prices[0];
        int profit = 0;
        for (int i = 1; i < prices.size(); i++) {
            if (prices[i] < start) start = prices[i];
            else if (prices[i] - start > profit) profit = prices[i] - start;
        }
        return profit;
    }
};

```
bedre å sjekke som profit, en d jeg holdt på med.

# Referanse
