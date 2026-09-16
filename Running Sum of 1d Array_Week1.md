class Solution {
    public int[] runningSum(int[] nums) {

        for (int i = 1; i < nums.length; i++) {
            nums[i] = nums[i] + nums[i - 1];
        }

        return nums;
    }
}



output: 



<img width="484" height="346" alt="image" src="https://github.com/user-attachments/assets/293b29ee-bb97-4e55-a420-dc790a5b9832" />
