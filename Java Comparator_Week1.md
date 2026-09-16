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

        // Higher score first
        if (a.score != b.score) {
            return b.score - a.score;
        }

        // Same score -> alphabetical order
        return a.name.compareTo(b.name);
    }
}

public class Solution {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();

        Player[] players = new Player[n];

        for (int i = 0; i < n; i++) {
            String name = sc.next();
            int score = sc.nextInt();

            players[i] = new Player(name, score);
        }

        Arrays.sort(players, new Checker());

        for (Player p : players) {
            System.out.println(p.name + " " + p.score);
        }

        sc.close();
    }
}





output:





<img width="540" height="386" alt="image" src="https://github.com/user-attachments/assets/4a5ea7c9-ed17-4b1a-831e-8323e8bcf40d" />
