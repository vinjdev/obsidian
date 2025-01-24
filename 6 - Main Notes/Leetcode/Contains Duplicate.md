16/10/24 10:30
Tags: [[Programmering]]
___

# Contains Duplicate
```c++
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        int count = 0;
        for (int i = 1; i < nums.size(); i++) {
            for (int j = i - 1; j >= 0; j--) {
                if (nums[i] == nums[j]) 
                    return true;
            }
        }
        return false;
    }
};

```
denne algorimten er alt for treg
O(N^2)
```c++
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        sort(nums.begin(),nums.end());
        for (int i = 0; i < nums.size()-1; i++) {
            if (nums[i] == nums[i+1])
                return true;
        }
        return false;
    }
};
```

denne koden er mye bedre, sort er mye raskere enn å bruke en nested loop

O (n log n)

når en liste er n = 1000

vil listen over gjøre 1 000 000 operasjoner

mens andre vil bare gjøre 10 000 operasjoner



# Referanse
