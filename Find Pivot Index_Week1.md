class Solution {
    public int pivotIndex(int[] nums) {
        int totalSum = 0;

        // Calculate total sum
        for (int num : nums) {
            totalSum += num;
        }

        int leftSum = 0;

        // Find pivot index
        for (int i = 0; i < nums.length; i++) {
            int rightSum = totalSum - leftSum - nums[i];

            if (leftSum == rightSum) {
                return i;
            }

            leftSum += nums[i];
        }

        return -1;
    }
}



output:


<img width="401" height="316" alt="image" src="https://github.com/user-attachments/assets/dd9d384b-640e-4dd2-81a7-857b0a137a6c" />


