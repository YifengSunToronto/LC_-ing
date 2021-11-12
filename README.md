# LC_heading_out_off_the_wood
![image](https://user-images.githubusercontent.com/32372822/141412239-5a728bdc-0bfa-4dc9-bd8a-4866c7ee84ca.png)
    
    # Go through 2 tree roots and check if their subtrees are also the same
    def isSameTree(self, node_a, node_b):
        # Base
        if node_a is None and node_b is None:
            return True
        elif (node_a and not node_b) or (node_b and not node_a):
            return False
        
        if node_a.val == node_b.val and self.isSameTree(node_a.left, node_b.left) and self.isSameTree(node_a.right, node_b.right):
            return True
        return False
            
        
    def isSubtree(self, root: Optional[TreeNode], subRoot: Optional[TreeNode]) -> bool:
        # Travel through the node starting from the root.
        # If it is the same tree as subtree, then return True.
        # Otherwise, check with left and right subtree.
        
        # Base: They are the same tree
        if self.isSameTree(root, subRoot):
            return True
        # Other case: If subtree is the same as any subtree, then it's true
        if (root.left and self.isSubtree(root.left, subRoot)) or (root.right and self.isSubtree(root.right, subRoot)):
            return True
        return False
