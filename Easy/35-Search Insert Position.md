Given a sorted array of distinct integers and a target value, return the index if the target is found. 

If not, return the index where it would be if it were inserted in order.

You must write an algorithm with O(log n) runtime complexity.

 

Example 1:
```
Input: nums = [1,3,5,6], target = 5
Output: 2
```

刚发现这道题目好早以前用CPP写过，写了好几次都没通过？？？我当时的代码水平是有多差。


My Code:
```
impl Solution {
  pub fn search_insert(nums: Vec<i32>, target: i32) -> i32 {
    let mut start  = 0;
    let mut end = nums.len();
    let mut mid = start + (end - start)/2;

    if nums[0] >= target{
      return 0;
    }

    //二分查找
    while start<end-1
    {
        mid = start + (end - start)/2;
        
        if nums[mid] == target{
          return mid as i32;
        }else if nums[mid] > target{
          end = mid;
        }else{
          start = mid;
        }
    }

    end as i32
  }
}

```
