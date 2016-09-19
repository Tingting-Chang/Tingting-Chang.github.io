---
layout: inner
title: 'Binary Tree -- Leetcode'
date: 2016-09-16 13:26:34
categories: blog development
tags: leetcode binary tree algorithm
lead_text: 'All solutions and reviews about binary tree exercises on leetcode'
---

####104. Maximum Depth of Binary Tree

Given a binary tree, find its maximum depth.

The maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.

`fn(n) = 0, if n = null`

`fn(n) = 1 + max(fn(n.left, n.right))`                                                              

```
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number}
 */
var maxDepth = function(root) {
    return find(root);
    function find(node) {
      if (node === null) {
        return 0;
      }

      var nodeL = 1, nodeR = 1;
      if (node.left !== null) {
        nodeL += find(node.left);
      }

      if (node.right !== null) {
        nodeR += find(node.right);
      }

      return nodeL > nodeR ? nodeL : nodeR;
    }
};
```

####226. Invert Binary Tree

Exchange child of one node

```
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {TreeNode}
 */
var invertTree = function(root) {
    if ((root === null) || (root.left === null) && (node.right === null)) {
      return root;
    }

    var temp = root.left;
    root.left = invertTree(root.right);
    root.right = invertTree(temp);

    return root;
};
```

####100. Same Tree
Given two binary trees, write a function to check if they are equal or not.

Two binary trees are considered equal if they are structurally identical and the nodes have the same value.

```
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} p
 * @param {TreeNode} q
 * @return {boolean}
 */
var isSameTree = function(p, q) {
    if ((p === null) && (q === null)) {
      return true;
    }

    if (((p === null) && (q !== null)) || ((p !== null) && (q === null))) {
      return false;
    }

    if (p.val !== p.val) {
      return false;
    }

    return isSameTree(p.left, q.left) && isSameTree(p.right, q.right);
};
```
####235. Lowest Common Ancestor of a Binary Search Tree

Given a binary search tree (BST), find the lowest common ancestor (LCA) of two given nodes in the BST.

According to the definition of LCA on Wikipedia: “The lowest common ancestor is defined between two nodes v and w as the lowest node in T that has both v and w as descendants (where we allow a node to be a descendant of itself).”

```
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @param {TreeNode} p
 * @param {TreeNode} q
 * @return {TreeNode}
 */
var lowestCommonAncestor = function(root, p, q) {
    if ((root === null) || (root === p) || (root === q)) {
      return root;
    }

    if ((root.val >= p.val && root.val <= q.val) || (root.val <= p.val && root.val >= q.val)) {
      return root;
    }

    if (root.val > p.val && root.val > q.val) {
      return lowestCommonAncestor(root.left, p, q);
    } else {
      return lowestCommonAncestor(root.right, p, q);
    }
};
```

####102. Binary Tree Level Order Traversal
Given a binary tree, return the level order traversal of its nodes' values. (ie, from left to right, level by level).

For example:
Given binary tree [3,9,20,null,null,15,7],

```
    3
   / \
  9  20
    /  \
   15   7
   
return its level order traversal as:
[
  [3],
  [9,20],
  [15,7]
]

```

```
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number[][]}
 */
var levelOrder = function(root) {
    // Check if it is an empty tree
    if (root === null || root.length === 0) {
      return [];
    }

    // Save data into a map{[level:x, node:y]}
    // Save node into a waittingList temporarily; the first node must be root with level 0
    var map = {},
        waittingList = [{level:0, node:root}];

    while(waittingList.length > 0) {
      var cur = waittingList.pop(), // Get the last item of waittingList
          node = cur.node;

      if (!map[cur.level]) { // If map does not have the level of the current node, then build a new level and save the node 
        map[cur.level] = [node.val]; // Notice that there are multiple nodes on one level, so we have to save it in an array
      } else { // If map does have the level, then save the node to the current level
        map[cur.level].push(node.val);
      }

      // Save the children nodes in waittingList but notice we always get the last item of the waittingList so we save right node first
      if (node.right) { // If the node has right child, save the right child under a new level
        waittingList.push({level: cur.level + 1, node: node.right});
      }

      if (node.left) { // If the node has left child, save the left child under a new level
        waittingList.push({level: cur.level + 1, node: node.left});
      }
    }

    // Save the result and return it
    var result = [];

    for (var i in map) {
      result.push(map[i]); // Notice that map is an object instead of function, so we need to use [] instead of ()
    }

    return result;
};
```

####107. Binary Tree Level Order Traversal II

Given a binary tree, return the bottom-up level order traversal of its nodes' values. (ie, from left to right, level by level from leaf to root).

For example:
Given binary tree [3,9,20,null,null,15,7],

```
    3
   / \
  9  20
    /  \
   15   7
   
return its bottom-up level order traversal as:
[
  [15,7],
  [9,20],
  [3]
]

```

```
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {number[][]}
 */
var levelOrderBottom = function(root) {
    // This is almost the same with 102. Binary Tree Level Order Traversal; we only need to reverse the result array
    // Recursive method

    if (root === null || root.length === 0) {
      return [];
    }

    var result = [], 
        map = {};

    // Initialize find funciton: root, level=0
    find (root, 0);

    for (var i in map) {
      result.push(map[i]);
    }

    return result.reverse();

    function find(node, level) {
      // Funciton find works the same as the waittingList
      if (node === null) {
        return null;
      }

      if (!map[level]) {
        map[level] = [node.val];
      } else {
        map[level].push(node.val);
      }      

      // Left first, right last
      find(node.left, level + 1);
      find(node.right, level + 1);
    }
};
```

####101. Symmetric Tree
Given a binary tree, check whether it is a mirror of itself (ie, symmetric around its center).

For example, this binary tree [1,2,2,3,4,4,3] is symmetric:

```
    1
   / \
  2   2
 / \ / \
3  4 4  3

But the following [1,2,2,null,3,null,3] is not:
    1
   / \
  2   2
   \   \
   3    3
   
```

```
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {boolean}
 */
var isSymmetric = function(root) {
    // First, reverse the right tree
    // Second, compare the left and right tree to see whether they are the same

    if (root === null || (root.left === null && root.left === null)) {
      return true;
    }

    root.right = revertTree(root.right);
    return isSameTree(root.left, root.right);

    function revertTree(node) {
      if (node === null || node.left === null && node.right === null) {
        return node;
      }

      var temp = revertTree(node.left);
      node.left = revertTree(node.right);
      node.right = temp;

      return node;
    }

    function isSameTree(left, right) {
      if (left === null && right === null) {
        return true;
      }

      if ((left !== null && right === null) || (left === null && right !== null)) {
        return false;
      }

      if (left.val !== right.val) {
        return false;
      }

      return isSameTree(left.right, right.right) && isSameTree(left.left, right.left);
    }
};
```