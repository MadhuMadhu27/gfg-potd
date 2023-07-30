## GFG Problem Of The Day

### 🎉 Announcement
I have created a Git Book that contains all previous editorials for my GFG-POTD solutions. You can visit **[here](https://gl01.gitbook.io/gfg-editorials/)** to access it and refer to my previous solutions. In the future, I intend to establish a contribution flow, where others can contribute their solutions to this Git Book. I would appreciate hearing your thoughts and views on this in the [discussion section](https://github.com/getlost01/gfg-potd/discussions).

----
### Today - 30 July 2023
### Que - Inorder Successor in BST

The problem can be found at the following link: [Question Link](https://practice.geeksforgeeks.org/problems/inorder-successor-in-bst/1)

### My Approach

To find the inorder successor of a given node `x` in a Binary Search Tree (BST), we can perform an inorder traversal of the BST while keeping track of the previously visited node (`prev`). When we encounter the node `x`, the next node visited in the inorder traversal will be its inorder successor.

### Explanation

- We start by defining a helper function `inorder` that performs the inorder traversal and finds the inorder successor of the given node `x`.
- In the `inorder` function, we recursively traverse the BST in an inorder fashion (left subtree, current node, right subtree).
- During the traversal, we compare each previous node with the given node `x`.
- If we find the node `x`, we set the `succ` pointer to the current node `root`(which will be the inorder successor).
- Before moving to the next node in the inorder traversal, we update the `prev` pointer to the current node.
- Once the traversal is complete, we return the `succ` pointer, which will hold the inorder successor of `x`.

### Time and Auxiliary Space Complexity

- **Time Complexity**: The time complexity of the `inorder` function is `O(N)`, where `N` is the number of nodes in the BST.

- **Auxiliary Space Complexity**: The auxiliary space complexity of the `inorder` function is `O(H)`, where `H` is the height of the BST. 

### Code (C++)

```cpp
class Solution {
public:
    Node* succ;

    void inorder(Node* root, Node* x, Node* &prev) {
        if (!root)
            return;
        
        inorder(root->left, x, prev);

        if (prev == x)
            succ = root;
        
        prev = root;
        inorder(root->right, x, prev);
    }

    Node* inOrderSuccessor(Node* root, Node* x) {
        Node* prev = NULL;
        succ = NULL;
        inorder(root, x, prev);
        return succ;
    }
};
```
### Contribution and Support

I always encourage contributors to participate in the discussion forum for this repository.

If you have a better solution or any queries / discussions related to the `Problem of the Day` solution, please visit our [discussion section](https://github.com/getlost01/gfg-potd/discussions). We welcome your input and aim to foster a collaborative learning environment.

If you find this solution helpful, consider supporting us by giving a `⭐ star` to the [getlost01/gfg-potd](https://github.com/getlost01/gfg-potd) repository.


![Total number of repository visitors](https://komarev.com/ghpvc/?username=gl01potdgfg&color=blue&&label=Visitors)
