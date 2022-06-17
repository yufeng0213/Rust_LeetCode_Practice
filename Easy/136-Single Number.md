Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

 

Example 1:
```
Input: nums = [2,2,1]
Output: 1
```

My Code:

```
use std::collections::HashMap;

impl Solution {
  pub fn single_number(nums: Vec<i32>) -> i32 {
    let mut hashNums:HashMap<i32,i32> = HashMap::new();

    let mut dstSize = 0;
    for &index in &nums{
      let count = hashNums.entry(index).or_insert(0);
      *count+=1;
    }

    for (key, value) in &hashNums {
      if *value == 1{
        let mut dstS = *key;
        return dstS;
      }
    }
    dstSize
  }
}

```
