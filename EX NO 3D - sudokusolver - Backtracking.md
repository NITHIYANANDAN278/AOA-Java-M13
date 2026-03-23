
# EX 3D Sudoku solver - Backtracking.
## DATE: 23/02/2026
## AIM:
To write a Java program to solve a Sudoku puzzle by filling the empty cells.

For example:
<img width="357" height="322" alt="image" src="https://github.com/user-attachments/assets/334b8c39-d547-4743-aca0-de92e38bdd1c" />



## Algorithm
1. Start the program and read a 9×9 Sudoku board input, where empty cells are represented by 0.
2. Define a function isSafe() to check if a number can be placed in a cell without violating Sudoku rules (row, column, and 3×3 box).
3. Use the recursive function solveSudoku() to fill empty cells one by one using backtracking.
4. If the number placement leads to a valid configuration, continue recursively; otherwise, backtrack by resetting the cell to 0.
5. After solving, print the completed Sudoku board if a solution exists; otherwise, display "No solution exists."
## Program:
```
/*
Program to implement Reverse a String
Developed by: Nithiyanandan N
Register Number: 212222230099
import java.util.Scanner;

public class SudokuSolver {

    // Check if it's safe to place the number
    static boolean isSafe(int[][] board, int row, int col, int num) {
        // Check row and column
        for (int i = 0; i < 9; i++) {
            if (board[row][i] == num || board[i][col] == num)
                return false;
        }

        // Check 3x3 subgrid
        int startRow = row - row % 3;
        int startCol = col - col % 3;

        for (int i = 0; i < 3; i++)
            for (int j = 0; j < 3; j++)
                if (board[startRow + i][startCol + j] == num)
                    return false;

        return true;
    }

    // Recursive backtracking solver
    static boolean solveSudoku(int[][] board, int row, int col) {
        //Type your code here
        if(row==9){
            return true;
        }
        if(col==9){
            return solveSudoku(board , row+1,0);
        }
        if(board[row][col] != 0){
    return solveSudoku(board , row , col+1);
}
        for(int i =1;i<=9;i++){
            if(isSafe(board , row , col, i)){
                board[row][col]=i;
                if(solveSudoku(board, row ,col+1)){
                    return true;
                }
                board[row][col]=0;
            }
        }
        return false;
    }

    // Utility to print the board
    static void printBoard(int[][] board) {
        for (int[] row : board) {
            for (int val : row)
                System.out.print(val + " ");
            System.out.println();
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int[][] board = new int[9][9];

      //  System.out.println("Enter the Sudoku puzzle row by row (use 0 for empty cells):");

        for (int i = 0; i < 9; i++) {
            //System.out.print("Enter row " + (i + 1) + ": ");
            for (int j = 0; j < 9; j++) {
                board[i][j] = sc.nextInt();
            }
        }

      //  System.out.println("\nSolving...\n");

        if (solveSudoku(board, 0, 0)) {
            System.out.println("Solved Sudoku:");
            printBoard(board);
        } else {
            System.out.println("No solution exists.");
        }

        sc.close();
    }
}
  
*/
```

## Output:
<img width="667" height="619" alt="image" src="https://github.com/user-attachments/assets/75c437f6-9a5d-4f41-b854-190175155a91" />



## Result:
The program successfully implemented and the expected output is verified.
