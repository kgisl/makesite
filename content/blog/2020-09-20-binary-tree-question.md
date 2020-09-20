<!-- title: Coding question -->

## BST question

You are asked to use an existing binary tree to generate a binary search tree (BST).

-   you have access to a node **root** which is the root node of a binary tree.
-   you have access to a function `is_valid(root)` which will return **true** if the node represents the root of a valid BST.
-   you have access to a function `preorder(root)` which will accept the root node of a **valid BST** and will return a list containing the values in the nodes as per the preorder traversal of the tree.
-   you also have access to a function `build_balanced_bst(alist)` which will return a valid and balanced BST containing all the values present in the list **alist**.

  
Write the code snippet that will take an existing binary tree and the above described functions to generate a valid binary search tree (BST).


```







































```







### Answer 
We can ignore whether a binary tree is a valid BST or not. Just **sort** the list and build a balanced BST out of it.

  
```python
  alist = preorder(root)
  alist.sort()
  bbst = build_balanced_bst(alist)
  print("generated BBST", bbst)
```

