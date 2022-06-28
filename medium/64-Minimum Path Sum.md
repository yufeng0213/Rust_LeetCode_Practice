

Given a m x n grid filled with non-negative numbers, find a path from top left to bottom right, which minimizes the sum of all numbers along its path.

Note: You can only move either down or right at any point in time.

My Code:
```
use std::cmp;
impl Solution {
  pub fn min_path_sum(grid: Vec<Vec<i32>>) -> i32 {
    let m = grid.len();
    let n = grid[0].len();
    let mut gridA = grid.clone();
    for row in 0..m{
      for col in 0..n{
        if row == 0 && col == 0{
          continue;
        }else if row == 0{
          gridA[row][col] += gridA[row][col-1];
        }else if col == 0{
          gridA[row][col] += gridA[row-1][col];
        }else{
          gridA[row][col] += cmp::min(gridA[row][col-1], gridA[row-1][col]); 
        }
      }
    }

    gridA[m-1][n-1]

  }
}
```
