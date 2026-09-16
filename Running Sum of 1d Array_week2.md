class Solution {
    public int[] runningSum(int[] nums) {

        for (int i = 1; i < nums.length; i++) {
            nums[i] = nums[i] + nums[i - 1];
        }

        return nums;
    }
}



ouput:



<img width="448" height="379" alt="image" src="https://github.com/user-attachments/assets/26ae8176-7623-4855-92f9-d4b3d2a5ce9f" />
