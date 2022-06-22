Given an array of distinct integers candidates and a target integer target, return a list of all unique combinations of candidates where the chosen numbers sum to target. You may return the combinations in any order.

The same number may be chosen from candidates an unlimited number of times. Two combinations are unique if the frequency of at least one of the chosen numbers is different.

It is guaranteed that the number of unique combinations that sum up to target is less than 150 combinations for the given input.

 

Example 1:
```
Input: candidates = [2,3,6,7], target = 7
Output: [[2,2,3],[7]]
Explanation:
2 and 3 are candidates, and 2 + 2 + 3 = 7. Note that 2 can be used multiple times.
7 is a candidate, and 7 = 7.
These are the only two combinations.
```


My Code:
```
impl Solution {
  pub fn combination_sum(candidates: Vec<i32>, target: i32) -> Vec<Vec<i32>> {
      let mut dstVec:Vec<Vec<i32>> = Vec::new();

      let mut path:Vec<i32> = Vec::new();
      let mut len = candidates.len();
      let mut index = len - 1;
      Self::dfs_helper(&candidates,target,0,&mut path,&mut dstVec,len);
      dstVec
  }  
  fn dfs_helper(candidates: &Vec<i32>,target: i32, index :usize,path: &mut Vec<i32>,res: &mut Vec<Vec<i32>>,len: usize){

    if target < 0 {
      return;
    }else if target == 0{
      res.push(path.clone());
      return;  
    }

    //let end = index.clone();
    //let mut indexA = index;

    for ind in index..len{
      path.push(candidates[ind]);
      Self::dfs_helper(candidates,target - candidates[ind],ind,path,res,len);
      //indexA -= 1;
      path.pop();
    }
  }
}

```
