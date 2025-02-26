### 3SUM
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

