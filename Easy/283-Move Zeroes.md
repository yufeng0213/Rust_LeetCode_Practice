
Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.

My Code:

```
impl Solution {
  pub fn move_zeroes(nums: &mut Vec<i32>) {
      let mut zeroIndex : usize = 0;
      let mut nozeroIndex : usize = zeroIndex;

      while zeroIndex < nums.len() && nozeroIndex < nums.len(){
          if nums[zeroIndex] != 0{
            zeroIndex += 1;
            nozeroIndex = zeroIndex+1;
          }else{
            if nums[nozeroIndex] != 0{
              nums.swap(zeroIndex, nozeroIndex);
              zeroIndex += 1;
              
             // println!("{:?}",nums.clone());
            }

            nozeroIndex += 1;
          }  
      }

  }
}
```
