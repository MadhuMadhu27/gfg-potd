## GFG Problem Of The Day

### 🌟 Woohoo! Huge congrats, guys! 🎉 
> This repo hit a whopping `1Lakh` views in the last 6 months, averaging 600-900 views daily. 

> 🚀 Amazing achievement! 🥳

### Today - 20 January 2024
### Que - Distribute candies in a binary tree
The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/distribute-candies-in-a-binary-tree/1)

![](https://badgen.net/badge/Level/Hard/red)

### My Approach

To solve this problem, I followed the subsequent steps:

1. Traverse the binary tree in a recursive manner.
2. For each node, calculate the number of candies needed to distribute equally among its left and right subtrees.
3. Accumulate the total moves required during the traversal.

### Time and Auxiliary Space Complexity

- **Time Complexity**: The time complexity of this solution is `O(N)`, where N is the number of nodes in the binary tree. This is because we visit each node once.
- **Auxiliary Space Complexity**: The auxiliary space complexity is `O(H)`, where H is the height of the binary tree. This accounts for the recursive call stack.

### Code (C++)

```cpp
class Solution
{
public:
    int solve(Node* root, int& moves)
    {
        if (!root)
        {
            return 0;
        }

        int left = solve(root->left, moves);
        int right = solve(root->right, moves);
        moves += abs(left) + abs(right);

        return root->key - 1 + left + right;
    }
    int distributeCandy(Node* root)
    {
        int moves = 0;
        solve(root, moves);
        return moves;
    }
};
```

### Contribution and Support

I always encourage contributors to participate in the discussion forum for this repository.

If you have a better solution or any queries / discussions related to the `Problem of the Day` solution, please visit our [discussion section](https://github.com/getlost01/gfg-potd/discussions). We welcome your input and aim to foster a collaborative learning environment.

If you find this solution helpful, consider supporting us by giving a `⭐ star` to the [getlost01/gfg-potd](https://github.com/getlost01/gfg-potd) repository.

![Total number of repository visitors](https://komarev.com/ghpvc/?username=gl01potdgfg&color=blue&&label=Visitors)
![](https://hit.yhype.me/github/profile?user_id=79409258)

