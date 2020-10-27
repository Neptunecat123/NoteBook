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

### 二叉树的中序遍历

首先遍历左子树，然后访问根节点，最后遍历右子树。

### 二叉树的后序遍历

首先遍历左子树，然后遍历右子树，最后访问根节点。

### 层序遍历

层序遍历就是逐层遍历树结构。

