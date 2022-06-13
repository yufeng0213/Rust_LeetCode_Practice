You are given a string s and an integer array indices of the same length. 

The string s will be shuffled such that the character at the ith position moves to indices[i] in the shuffled string.

Return the shuffled string.

 

Example 1:

```
Input: s = "codeleet", indices = [4,5,6,7,0,2,1,3]
Output: "leetcode"
Explanation: As shown, "codeleet" becomes "leetcode" after shuffling.
```

My Code:
```
impl Solution {
  pub fn restore_string(s: String, indices: Vec<i32>) -> String {
    let lenA = indices.len();
    let mut dstStr : Vec<u8> = vec!['0' as u8;lenA];
    let my_bytes = s.into_bytes();
    
    for index in 0..lenA{
       dstStr[indices[index as usize] as usize] = my_bytes[index as usize];
    }

    String::from_utf8_lossy(&dstStr).to_string()
    
  }
}
```

Get new usage;

Other Code:
```
impl Solution {
  pub fn restore_string(s: String, indices: Vec<i32>) -> String {
    let mut dstVec = vec![' ';indices.len()];

    for (i,&d) in indices.iter().enumerate(){
        dstVec[d as usize] = s.as_bytes()[i] as char;
    }
    dstVec.iter().collect::<String>()
  }
}

```
