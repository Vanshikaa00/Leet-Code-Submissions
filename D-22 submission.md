# :zap: Question

> Given a binary tree, return the zigzag level order traversal of its nodes' values. (ie, from left to right, then right to left for the next level and alternate between).
```
For example:
Given binary tree [3,9,20,null,null,15,7],
    3
   / \
  9  20
    /  \
   15   7
return its zigzag level order traversal as:
[
  [3],
  [20,9],
  [15,7]
]
```

# :peach: Solution

```

    class Solution {
        public List<List<Integer>> zigzagLevelOrder(TreeNode root) {

            List<List<Integer>> zigzagLevelOrder = new ArrayList<>();

            if (root == null) return zigzagLevelOrder;

            Stack<TreeNode> currentLevel = new Stack<>();
            Stack<TreeNode> nextLevel = new Stack<>();

            currentLevel.push(root);

            while (!currentLevel.isEmpty()) {

                List<Integer> levelNodes = new ArrayList<>();

                while (!currentLevel.isEmpty()) {
                    TreeNode curr = currentLevel.pop();

                    levelNodes.add(curr.val);

                    if (curr.left != null) {
                        nextLevel.push(curr.left);
                    }
                    if (curr.right != null) {
                        nextLevel.push(curr.right);
                    }
                }

                zigzagLevelOrder.add(levelNodes);

                levelNodes = new ArrayList<>();

                while (!nextLevel.isEmpty()) {
                    TreeNode curr = nextLevel.pop();

                    levelNodes.add(curr.val);

                    if (curr.right != null) {
                        currentLevel.push(curr.right);
                    }
                    if (curr.left != null) {
                        currentLevel.push(curr.left);
                    }
                }

                if (!levelNodes.isEmpty()) zigzagLevelOrder.add(levelNodes);

            }

            return zigzagLevelOrder;
        }
    }

```
