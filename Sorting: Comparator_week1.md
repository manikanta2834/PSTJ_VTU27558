import java.util.*;

class Player {
    String name;
    int score;

    Player(String name, int score) {
        this.name = name;
        this.score = score;
    }
}

class Checker implements Comparator<Player> {

    @Override
    public int compare(Player a, Player b) {
        // Sort by score in descending order
        if (a.score != b.score) {
            return Integer.compare(b.score, a.score);
        }

        // If scores are equal, sort by name alphabetically
        return a.name.compareTo(b.name);
    }
}

public class Solution {

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);

        int n = scan.nextInt();
        Player[] players = new Player[n];

        for (int i = 0; i < n; i++) {
            String name = scan.next();
            int score = scan.nextInt();

            players[i] = new Player(name, score);
        }

        Arrays.sort(players, new Checker());

        for (Player player : players) {
            System.out.println(player.name + " " + player.score);
        }

        scan.close();
    }
}




output:





<img width="577" height="403" alt="image" src="https://github.com/user-attachments/assets/502e7650-20f9-47ec-9a09-6bbc7216b749" />
