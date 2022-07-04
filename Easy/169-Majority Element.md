

My Code:
```

use std::collections::HashMap;
impl Solution {
  pub fn majority_element(nums: Vec<i32>) -> i32 {
      let mut ans:HashMap<i32,i32> = HashMap::new();
      let mut dstValue = 0;
      let mut dstKey = 0;
      for index in nums{
          let count = ans.entry(index).or_insert(1);
          *count += 1;
      }


      for (key,value) in ans{
          if value > dstValue{
            dstKey = key;
            dstValue = value;
          }
      }

      dstKey
  }
}


```

优化后的：

```

```
