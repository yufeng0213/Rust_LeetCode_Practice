Determine if a 9 x 9 Sudoku board is valid. Only the filled cells need to be validated according to the following rules:

Each row must contain the digits 1-9 without repetition.
Each column must contain the digits 1-9 without repetition.
Each of the nine 3 x 3 sub-boxes of the grid must contain the digits 1-9 without repetition.
Note:

A Sudoku board (partially filled) could be valid but is not necessarily solvable.
Only the filled cells need to be validated according to the mentioned rules.


暴力解法又不是不能用......

My Code:

```
use std::collections::HashMap;
impl Solution {
  pub fn is_valid_sudoku(board: Vec<Vec<char>>) -> bool {
    let result = true;
    
    //row
    for row in 0..9{
      let mut tempHash:HashMap<char,i32> = HashMap::new();
      for col in 0..9{
        let count = tempHash.entry(board[row as usize][col as usize]).or_insert(0);
        *count+=1;
        if *count > 1 && board[row as usize][col as usize] != '.'{
          return false;
        }
      }
    }

    //col
    for col in 0..9{
      let mut tempHash:HashMap<char,i32> = HashMap::new();
      for row in 0..9{
        let count = tempHash.entry(board[row as usize][col as usize]).or_insert(0);
        *count+=1;
        if *count > 1 && board[row as usize][col as usize] != '.'{
          return false;
        }
      }
    }

    //3x3
    
    for ind in 0..3{
    
           
      //let mut indA = 0;
      
      for indA in 0..3{
        let mut tempHash:HashMap<char,i32> = HashMap::new(); 
        for row in (0+ind)*3..(0+ind)*3+3{
          for col in (0+indA)*3..(0+indA)*3+3{
              let count = tempHash.entry(board[row as usize][col as usize]).or_insert(0);
              *count+=1;
              if *count > 1 && board[row as usize][col as usize] != '.'{
              return false;
          }
        }
      }
      
    }
  }


    result

  }
}

```
