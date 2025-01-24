16/10/24 10:55
Tags: 
___

# SUM OF TWO INTEGERS

```c++
class Solution {
public:
    int getSum(int a, int b) {
        std::vector<int> nums = {a,b};

        int sum = std::accumulate(nums.begin(),nums.end(),0);
        return sum;
    }
};

```

spørte chatten om en algoritme for dette. ettersom jeg ikke vet hva noen av de algortihmene heter

## kan ogsp bruke bitwise:
```c++
while(b != 0) {
	int sum = a ^ b; // XOR
	int carry = (a & b) << 1; 
	a = sum;
	b = carry;
}
return a;
```
BRUKER CARRAY NÅR a og b ER DET *SAMME*


# Referanse
