
# EX 3E Generate Permutations using Backtracking  Approach.
## DATE: 24/02/2026
## AIM:
To write a Java program to for given constraints.
Given an array nums of distinct integers, return all the possible Permutation. You can return the answer in any order.
Example 1:
Input: nums = [1,2,3]
Output: [[1,2,3],[1,3,2],[2,1,3],[2,3,1],[3,1,2],[3,2,1]]
For example:
## Algorithm
1. Start the program and read the input array of integers from the user.
2. Initialize an empty list ans to store all possible permutations.
3. Use the recursive backtrack() method to build permutations by adding unused elements one by one.
4. When the current permutation length equals the array length, add it to the result list.
5. After recursion completes, print the list of all generated permutations.

## Program:
```
/*
Program to implement Reverse a String
Developed by: NITHIYANANDAN N
Register Number: 212222230099
import java.util.*;

public class Solution {

    public List<List<Integer>> permute(int[] nums) {
        //add your code here
        List<List<Integer>> ans = new ArrayList<>();
        backtrack(new ArrayList<>(),ans,nums);
        return ans;
    }

    public void backtrack(List<Integer> curr, List<List<Integer>> ans, int[] nums) {
        //Add your code here
        if(curr.size()==nums.length){
            ans.add(new ArrayList<>(curr));
        }
        for(int i=0;i<nums.length;i++){
            if(curr.contains(nums[i])){
                continue;
            }
            curr.add(nums[i]);
            backtrack(curr,ans,nums);
            curr.remove(curr.size()-1);
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String inputLine = scanner.nextLine().trim();
        inputLine = inputLine.replaceAll(".*\\[|\\].*", ""); 
        String[] parts = inputLine.split(",");

        int[] nums = new int[parts.length];
        for (int i = 0; i < parts.length; i++) {
            nums[i] = Integer.parseInt(parts[i].trim());
        }
        Solution solution = new Solution();
        List<List<Integer>> permutations = solution.permute(nums);
        System.out.println(permutations);
        scanner.close();
    }
}
 
*/
```

## Output:
<img width="1144" height="165" alt="image" src="https://github.com/user-attachments/assets/f32695cc-3963-45ff-9b2a-24c590b98037" />



## Result:
The program successfully implemented and the expected output is verified.
