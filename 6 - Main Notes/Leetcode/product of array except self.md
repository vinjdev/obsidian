16/10/24 11:12
Tags: [[Programmering]]
___

# product of array except self
```c++
class Solution {

public:

vector<int> productExceptSelf(vector<int>& nums){

int n = nums.size();

vector<int> answer(n,1);

  

for(int i = 1; i < n; i++)

answer[i] = answer[i-1] * nums[i-1];

  

int R = 1;

for (int i = n-1; i >= 0; i--) {

answer[i] = answer[i] * R;

R *= nums[i];

}

return answer;

}

};
```

skjønner ikke hvordan prefix og suffix fungerer da...



# Referanse
