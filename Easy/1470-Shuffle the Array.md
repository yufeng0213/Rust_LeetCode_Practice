Given the array nums consisting of 2n elements in the form [x1,x2,...,xn,y1,y2,...,yn].

Return the array in the form [x1,y1,x2,y2,...,xn,yn].

Example 1:
```
Input: nums = [2,5,1,3,4,7], n = 3 

Output: [2,3,5,4,1,7] 

Explanation: Since x1=2, x2=5, x3=1, y1=3, y2=4, y3=7 then the answer is [2,3,5,4,1,7].
```

My Code:

```
impl Solution {
    pub fn shuffle(nums: Vec<i32>, n: i32) -> Vec<i32> {
        let mut result = vec![0;n as usize*2];
        let un = n as usize;
        for index in 0..un{
            result[index*2] = nums[index];
            result[index*2+1] = nums[index+un];
        }
        
        result
    }
}
```
