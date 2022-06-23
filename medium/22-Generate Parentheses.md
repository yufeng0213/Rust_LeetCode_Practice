Given n pairs of parentheses, write a function to generate all combinations of well-formed parentheses.

 

Example 1:
```
Input: n = 3
Output: ["((()))","(()())","(())()","()(())","()()()"]
```

My Code:
```
impl Solution{
  
  fn dfs_helper(dstStr:String,open: i32,close: i32) -> Vec<String>{

    let mut res = vec![];

    if close == 0 && open == 0{
        return vec![dstStr];
    }

    if open > 0{
      res.append(&mut Self::dfs_helper(dstStr.clone()+"(",open - 1,close+1));
    }

    if close > 0{
      res.append(&mut Self::dfs_helper(dstStr.clone()+")",open,close-1));
    }

    res

  }

  pub fn generate_parenthesis(n:i32) -> Vec<String>{
    let mut dstVec:Vec<String> =  Vec::new();

    Self::dfs_helper("".to_string(),n,0)
  }
}
```
