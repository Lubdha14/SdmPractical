3SUM


class Solution {
    public List<List<Integer>> threeSum(int[] nums) {
        List<List<Integer>>result = new ArrayList<>();
        Arrays.sort(nums);
        for(int i=0; i<nums.length-2; i++){
            if(i>0 && nums[i]==nums[i-1]){
                continue;
            }
            int left = i+1;
            int right = nums.length-2;
            while(left<right){
                int sum = nums[i]+nums[left]+nums[right];
                if(sum==0)
                {
                    result.add(Arrays.asList(nums[i],nums[left],nums[right]));
                
                left++;
                right--;
                
                while(left<right && nums[left]==nums[left-1]){
                    left++;
                }
                while(left<right && nums[right]==nums[right-1]){
                    right--;
                }
                }
                else if(sum<0){
                left++;
                }else{
                right++;
                }
        }
        }
       return result;
    }
}

========================================================================================
560. Subarray Sum Equals K

class Solution {
    public int subarraySum(int[] nums, int k) {
        int a1[]= new int[2];
        int count=0;
        // int right = arr.length;
        for(int i=0; i<nums.length;i++){
            int n =0;
            for(int j=i; j<nums.length;j++){
                n = n+nums[j];
                if(n == k){
                    count++;
                }
            }
        }
        return count;
    }
}
=====================================================================================
53. Maximum Subarray

class Solution {
    public int maxSubArray(int[] nums) {
        // Initialize max to the first element of the array
        int max = nums[0];
        // Iterate through all possible starting points of subarrays
        for (int i = 0; i < nums.length; i++) {
            int currentSum = 0; // Initialize currentSum for each starting point
            // Iterate through all possible ending points of subarrays
            for (int j = i; j < nums.length; j++) {
                currentSum += nums[j]; // Add the current element to the currentSum
                // Update max if currentSum is greater
                if (currentSum > max) {
                    max = currentSum;
                }
            }
        }
        return max; // Return the maximum subarray sum
    }
}
===========================
lubdha=
class Solution {
    public int maxSubArray(int[] nums) {
        
        
        int max=nums[0];
        for(int i=0;i<nums.length;i++)
        {
            int sum=0;
        for(int j=1; j<nums.length; j++){
            sum += nums[j];
            if(sum>max)
            {
                max=sum;
            }
        }
        }
        return max;
    }
}=====================================================================
##11. Container With Most Water
class Solution {
    public int maxArea(int[] height) {
        int left = 0; // Initialize left pointer
        int right = height.length - 1; // Initialize right pointer
        int maxArea = 0; // Variable to store the maximum area
        // Loop until the two pointers meet
        while (left < right) {
            // Calculate the width between the two pointers
            int width = right - left;
            // Calculate the height as the minimum of the two heights
            int currentHeight = Math.min(height[left], height[right]);
            // Calculate the area
            int currentArea = width * currentHeight;
            // Update maxArea if the current area is larger
            maxArea = Math.max(maxArea, currentArea);
            // Move the pointer pointing to the shorter line inward
            if (height[left] < height[right]) {
                left++; // Move left pointer to the right
            } else {
                right--; // Move right pointer to the left
            }
        }
        return maxArea; // Return the maximum area found
    }
}
===================================================









ARRAY
	
1. 3Sum
•	Problem: Given an integer array nums, return all unique triplets [nums[i], nums[j], nums[k]] such that i != j != k and nums[i] + nums[j] + nums[k] == 0.
•	Difficulty: Medium
•	Link: 3Sum
•	Concepts Tested: Sorting, Two-pointer technique, Hashing
2. Subarray Sum Equals K
•	Problem: Given an array of integers nums and an integer k, return the total number of continuous subarrays whose sum equals to k.
•	Difficulty: Medium
•	Link: Subarray Sum Equals K
•	Concepts Tested: Prefix Sum, HashMap, Sliding Window
3. Product of Array Except Self
•	Problem: Given an array nums of n integers where n > 1, return an array such that each element at index i is the product of all the numbers in the array except the one at i.
•	Difficulty: Medium
•	Link: Product of Array Except Self
•	Concepts Tested: Prefix and Suffix Arrays, Division (if allowed), Two-pass solution
4. Maximum Subarray (Kadane's Algorithm)
•	Problem: Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.
•	Difficulty: Medium
•	Link: Maximum Subarray
•	Concepts Tested: Dynamic Programming, Kadane's Algorithm
5. Container With Most Water
•	Problem: Given n non-negative integers a1, a2, ..., an where each represents a point at coordinate (i, ai), find two lines that together with the x-axis form a container, such that the container contains the most water.
•	Difficulty: Medium
•	Link: Container With Most Water
•	Concepts Tested: Two-pointer technique, Greedy Approach

STRING
1. Longest Substring Without Repeating Characters
•	Problem: Given a string s, find the length of the longest substring without repeating characters.
•	Difficulty: Medium
•	Link: Longest Substring Without Repeating Characters
•	Concepts Tested: Sliding window, HashMap, Two pointers
2. Valid Anagram
•	Problem: Given two strings s and t, return true if t is an anagram of s and false otherwise.
•	Difficulty: Medium
•	Link: Valid Anagram
•	Concepts Tested: HashMap, Sorting, Frequency count
3. Group Anagrams
•	Problem: Given an array of strings, group the anagrams together. You can return the answer in any order.
•	Difficulty: Medium
•	Link: Group Anagrams
•	Concepts Tested: Hashing, Sorting, HashMap
4. Longest Palindromic Substring
•	Problem: Given a string s, return the longest palindromic substring in s.
•	Difficulty: Medium
•	Link: Longest Palindromic Substring
•	Concepts Tested: Dynamic Programming, Expand Around Center, Sliding window
5. String to Integer (atoi)
•	Problem: Implement the myAtoi(string s) function, which converts a string to a 32-bit signed integer, handling leading whitespace, sign, and numeric characters while ignoring non-numeric characters.
•	Difficulty: Medium
•	Link: String to Integer (atoi)
•	Concepts Tested: String manipulation, Handling edge cases, Handling overflow and underflow




