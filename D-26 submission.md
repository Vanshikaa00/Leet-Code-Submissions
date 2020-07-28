# :zap: Question
> Given inorder and postorder traversal of a tree, construct the binary tree.
> Note:
> You may assume that duplicates do not exist in the tree.
> For example, given
> inorder = [9,3,15,20,7]
> postorder = [9,15,7,20,3]
> Return the following binary tree:
```
    3
   / \
  9  20
    /  \
   15   7
   ```
   
   # :peach: Solution
   ```
   class Solution {
    
    HashMap<Integer,Integer> map=null;
    int post_index=0;
    
    public TreeNode buildTree(int[] inorder, int[] post) {
        map=new HashMap<>();
        post_index=post.length-1;
        
        for(int i=0;i<inorder.length;i++){
            map.put(inorder[i],i);
        }
        return construct(post,0,inorder.length-1);
    }
    
    public TreeNode construct(int[] post,int instart,int inend){
        if(instart>inend) return null;
        
        int index=map.get(post[post_index]);
                
        TreeNode root=new TreeNode(post[post_index]);
        
        post_index--;
        
        root.right=construct(post,index+1,inend);
        root.left=construct(post,instart,index-1);
         
        return root;
    }
}

   ```
