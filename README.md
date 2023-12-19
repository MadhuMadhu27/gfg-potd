## GFG Problem Of The Day

### Today - 19 December 2023
### Que - Rightmost different bit
The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/rightmost-different-bit-1587115621/1)

![](https://badgen.net/badge/Level/Easy/green)

### My Approach
- Calculate the bitwise XOR of `m` and `n` to find the bits that are different.
- Find the rightmost set bit in the XOR result using the expression `res = res & (-res)`.
- Return the position (1-based) of the rightmost set bit.

### Time and Auxiliary Space Complexity

- **Time Complexity**: O(1)
- **Auxiliary Space Complexity**: O(1)

### Code (C++)
```cpp
class Solution {
public:
    int posOfRightMostDiffBit(int m, int n) {
        if (m == n)
            return -1;
            
        int res = m ^ n;
        res = res & (-res);
        return log2(res) + 1;
    }
};
```
### Contribution and Support

I always encourage contributors to participate in the discussion forum for this repository.

If you have a better solution or any queries / discussions related to the `Problem of the Day` solution, please visit our [discussion section](https://github.com/getlost01/gfg-potd/discussions). We welcome your input and aim to foster a collaborative learning environment.

If you find this solution helpful, consider supporting us by giving a `⭐ star` to the [getlost01/gfg-potd](https://github.com/getlost01/gfg-potd) repository.

![Total number of repository visitors](https://komarev.com/ghpvc/?username=gl01potdgfg&color=blue&&label=Visitors)
![](https://hit.yhype.me/github/profile?user_id=79409258)

