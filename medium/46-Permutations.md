Given an array nums of distinct integers, return all the possible permutations. You can return the answer in any order.

 

Example 1:
```
Input: nums = [1,2,3]
Output: [[1,2,3],[1,3,2],[2,1,3],[2,3,1],[3,1,2],[3,2,1]]
```

My Code:
```
impl Solution {
  
  fn dfs_helper(count: usize,res:&mut Vec<Vec<i32>>,tempVec:&mut Vec<i32>,nums:&mut Vec<i32>,isUse:&mut Vec<bool>){
    
    if count == 0{
      res.push(tempVec.clone());
    
   
        return;
    }

    for index in 0..nums.len(){

      let mut tempIsUse:Vec<bool> = isUse.clone();
      if tempIsUse[index] {
        continue;
      }
    
      let mut tempNums = nums.clone();
        
     
      let mut tempVVec:Vec<i32> =tempVec.clone();
      let mut t = tempNums[index];
      tempVVec.push(t);
      tempIsUse[index] = true;
    
        
      Self::dfs_helper(count-1,res,&mut tempVVec,&mut tempNums,&mut tempIsUse);
    }

  }
  
  pub fn permute(nums: Vec<i32>) -> Vec<Vec<i32>> {
    
    let mut dstVec:Vec<Vec<i32>> = Vec::new();
    let mut tempNums = nums.clone();
    let mut isUse :Vec<bool> = vec![false;nums.len()]; 

    Self::dfs_helper(nums.len(),&mut dstVec,&mut Vec::new(),&mut tempNums,&mut isUse);

    dstVec

  }
}
```
