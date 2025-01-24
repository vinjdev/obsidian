15/10/24 11:48
Tags: [[Programmering]]
___

# TWO SUM

nested loop, men sjekker alltid elementet ETTER den jeg er på

HUSK at SIZE er -1 i første og vanlig i ANDRE

```c++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        for (int i = 0; i < nums.size() - 1; i++) {
            for (int j = i + 1; j < nums.size();j++ )
                if (nums[i]+nums[j] == target) {
                    return { i,j };
                }
        }
        return {};
    }
};

```



# Referanse
