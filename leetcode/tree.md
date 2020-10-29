# 树

树里的每一个节点有一个值和一个包含所有子节点的列表。从图的观点看，树可以视为一个拥有N个节点和N-1条边的有向无环图。

二叉树是一种典型的树状结构，每个节点最多有两个子树的树结构。

## 树的遍历

### 二叉树的前序遍历

首先访问根节点，然后遍历左子树，最后遍历右子树。

例题：

给定一个二叉树，返回它的前序遍历。

输入: [1,null,2,3]  
   1
    \
     2
    /
   3 

输出: [1,2,3]

**法1：递归**

    # Definition for a binary tree node.
    # class TreeNode:
    #     def __init__(self, val=0, left=None, right=None):
    #         self.val = val
    #         self.left = left
    #         self.right = right
    class Solution:
        def preorderTraversal(self, root: TreeNode) -> List[int]:
            def preorder(root):
                if not root:
                    return
                res.append(root.val)
                preorder(root.left)
                preorder(root.right)

            res = list()
            preorder(root)
            return res

**法2：迭代**

    # Definition for a binary tree node.
    # class TreeNode:
    #     def __init__(self, val=0, left=None, right=None):
    #         self.val = val
    #         self.left = left
    #         self.right = right
    class Solution:
        def preorderTraversal(self, root: TreeNode) -> List[int]:
            if root is None:
                return
            stack, res = [root,], []
            while stack:
                root = stack.pop()
                if root:
                    res.append(root.val)
                    if root.right:
                        stack.append(root.right)
                    if root.left:
                        stack.append(root.left)
            return res

### 二叉树的中序遍历

首先遍历左子树，然后访问根节点，最后遍历右子树。

### 二叉树的后序遍历

首先遍历左子树，然后遍历右子树，最后访问根节点。

### 层序遍历

层序遍历就是逐层遍历树结构。

[102 二叉树的层序遍历](https://leetcode-cn.com/problems/binary-tree-level-order-traversal/)

给你一个二叉树，请你返回其按 层序遍历 得到的节点值。 （即逐层地，从左到右访问所有节点）。

示例：
二叉树：[3,9,20,null,null,15,7],

     3
    / \
    9  20
      /  \
     15   7
返回其层次遍历结果：

    [
        [3],
        [9,20],
        [15,7]
    ]

解答：

    # Definition for a binary tree node.
    # class TreeNode:
    #     def __init__(self, x):
    #         self.val = x
    #         self.left = None
    #         self.right = None
    from collections import deque
    class Solution:
        def levelOrder(self, root: TreeNode) -> List[List[int]]:
            res = []
            q = deque()
            if not root:
                return []
            q.append(root)
            while q:
                q_len = len(q)
                level = []
                for i in range(q_len):
                    node = q.pop()
                    level.append(node.val)
                    if node.left:
                        q.appendleft(node.left)
                    if node.right:
                        q.appendleft(node.right)
                res.append(level)
            return res

## 深度优先搜索DFS

大致dfs分析。

[129 求根到叶子节点数字之和](https://leetcode-cn.com/problems/sum-root-to-leaf-numbers)

给定一个二叉树，它的每个结点都存放一个 0-9 的数字，每条从根到叶子节点的路径都代表一个数字。

例如，从根到叶子节点路径 1->2->3 代表数字 123。

计算从根到叶子节点生成的所有数字之和。

说明: 叶子节点是指没有子节点的节点。

示例 1:

    输入: [1,2,3]
        1
       / \
      2   3
    输出: 25
    解释:
    从根到叶子节点路径 1->2 代表数字 12.
    从根到叶子节点路径 1->3 代表数字 13.
    因此，数字总和 = 12 + 13 = 25.

示例 2：

    输入: [4,9,0,5,1]
        4
       / \
      9   0
     / \
    5   1
    输出: 1026
    解释:
    从根到叶子节点路径 4->9->5 代表数字 495.
    从根到叶子节点路径 4->9->1 代表数字 491.
    从根到叶子节点路径 4->0 代表数字 40.
    因此，数字总和 = 495 + 491 + 40 = 1026.

解答，递归：

    # Definition for a binary tree node.
    # class TreeNode:
    #     def __init__(self, x):
    #         self.val = x
    #         self.left = None
    #         self.right = None

    class Solution:
        def sumNumbers(self, root: TreeNode) -> int:
            def dfs(root: TreeNode, prev_total: int):
                if not root:
                    return 0
                total = prev_total*10 + root.val
                if not root.left and not root.right:
                    return total
                else:
                    return dfs(root.left, total) + dfs(root.right, total)

            return dfs(root, 0)




## 广度优先搜索BFS

pass
