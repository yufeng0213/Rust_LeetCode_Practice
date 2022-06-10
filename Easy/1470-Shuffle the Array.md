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
