Given the root of a binary tree, return the inorder traversal of its nodes' values.

中序遍历


My Code:
```
use std::rc::Rc;
use std::cell::{RefCell,Ref};
impl Solution {
    pub fn inorder_traversal(root: Option<Rc<RefCell<TreeNode>>>) -> Vec<i32> {
        
      let mut dstVec:Vec<i32> = Vec::new();

      fn search_tree(node: Option<Rc<RefCell<TreeNode>>>,res:&mut Vec<i32>){
         if let Some(n) = node{
            search_tree(n.borrow().left.clone(), res);
            res.push(n.borrow().val);
            search_tree(node.borrow().right.clone(), res);
         }
      }

      search_tree(root, &mut dstVec);
      dstVec

    }
}
```
