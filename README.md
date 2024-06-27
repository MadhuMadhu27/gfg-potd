## GFG Problem Of The Day

### Today - 03 June 2024
### Que - Trail of ones
The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/trail-of-ones3242/1)

### My Approach
- Initialize `mod` to (10^9 + 7) to handle large numbers and prevent overflow.
- Initialize `out` to 1, which will store the number of valid sequences of ones.
- Initialize `x` to 0 and `y` to 1, representing the number of valid sequences ending in a single one or two consecutive ones respectively.
- Iterate from 3 to `n`:
  - Update `out` to `(out * 2 + x + y) % mod` to include new sequences formed by appending "0" or "1" to previous valid sequences.
  - Temporarily store the current value of `x` in `z`.
  - Update `x` to the current value of `y`.
  - Update `y` to `(x + z) % mod`, maintaining the count of sequences ending in two consecutive ones.
- Return the final value of `out`.

### Time and Auxiliary Space Complexity

- **Time Complexity**: `(O(n))`, since we iterate from 3 to `n`.
- **Auxiliary Space Complexity**: `(O(1))`, as we use a constant amount of extra space regardless of the input size.

### Code (C++)
```cpp
class Solution {
public:
    int numberOfConsecutiveOnes(int n) {
        int mod = 1e9 + 7;
        long out = 1;
        int x = 0, y = 1;
        for (int i = 3; i <= n; ++i) {
            out = (out * 2 + x + y) % mod;
            int z = x;
            x = y;
            y = (x + z) % mod;
        }
        return out;
    }
};
```

### Contribution and Support




I always encourage contributors to participate in the discussion forum for this repository.

If you have a better solution or any queries / discussions related to the `Problem of the Day` solution, please visit our [discussion section](https://github.com/getlost01/gfg-potd/discussions). We welcome your input and aim to foster a collaborative learning environment.

If you find this solution helpful, consider supporting us by giving a `⭐ star` to the [getlost01/gfg-potd](https://github.com/getlost01/gfg-potd) repository.

![Total number of repository visitors](https://komarev.com/ghpvc/?username=gl01potdgfg&color=blue&&label=Visitors)
![](https://hit.yhype.me/github/profile?user_id=79409258)



Given a number n, find the number of trailing ones in the factorial of n (denoted as n!).

Steps to Solve:
Calculate the factorial:

Factorial of n (denoted as n!) is the product of all positive integers less than or equal to n.
For example, 5! = 5 * 4 * 3 * 2 * 1 = 120.
Count the trailing ones:

Trailing ones are counted by looking at the end of the number in its decimal form.
For example, 120 has 0 trailing ones.
Solution in Python:
Here is a Python function that calculates the number of trailing ones in n!:
def factorial(n):
    if n == 0 or n == 1:
        return 1
    result = 1
    for i in range(2, n + 1):
        result *= i
    return result

def count_trailing_ones(n):
    fact = factorial(n)
    count = 0
    while fact % 10 == 1:
        count += 1
        fact //= 10
    return count

# Example usage
n = 5
print(f"The number of trailing ones in {n}! is {count_trailing_ones(n)}")
Explanation:
Refer to <a href="https://www.google.gl/url?sa=t&url=https://www.h2kinfosys.com/blog/python-tutorials/">Python Blog</a> to Know more.
Factorial function:
This function calculates the factorial of n by multiplying all integers from 2 to n.
Count trailing ones function:
After computing the factorial, it checks the number of trailing ones by repeatedly dividing the factorial result by 10 as long as the last digit is 1.
Note:
Typically, factorial numbers end with a trailing zero rather than trailing ones because the multiplication involves 2s and 5s. Therefore, for most practical purposes, there won't be trailing ones.
The function provided here demonstrates the concept, but for realistic factorial values, this situation doesn't usually occur.

