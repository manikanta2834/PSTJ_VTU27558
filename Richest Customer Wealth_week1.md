class Solution {
    public int maximumWealth(int[][] accounts) {
        int maxWealth = 0;

        for (int i = 0; i < accounts.length; i++) {
            int wealth = 0;

            for (int j = 0; j < accounts[i].length; j++) {
                wealth += accounts[i][j];
            }

            maxWealth = Math.max(maxWealth, wealth);
        }

        return maxWealth;
    }
}


output:



<img width="485" height="317" alt="image" src="https://github.com/user-attachments/assets/655248c2-23a8-4f23-8338-6e1450147b07" />
