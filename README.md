import java.util.ArrayList;
import java.util.Scanner;

class Friend {
    String name;
    String birthday;

    public Friend(String name, String birthday) {
        this.name = name;
        this.birthday = birthday;
    }

    public String getName() {
        return name;
    }

    public String getBirthday() {
        return birthday;
    }
}

class FriendManager {
    private ArrayList<Friend> friendsList;

    public FriendManager() {
        friendsList = new ArrayList<>();
    }

    public void addFriend(String name, String birthday) {
        Friend friend = new Friend(name, birthday);
        friendsList.add(friend);
    }

    public void displayFriends() {
        System.out.println("Friends List:");
        for (Friend friend : friendsList) {
            System.out.println("Name: " + friend.getName() + ", Birthday: " + friend.getBirthday());
        }
    }
}

public class SocialProblemSolution {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        FriendManager friendManager = new FriendManager();

        // Adding friends to the list
        friendManager.addFriend("james", "2009-05-15");
        friendManager.addFriend("kevin", "2008-12-03");

        // Displaying the initial friends list
        friendManager.displayFriends();

        // Adding a new friend based on user input
        System.out.println("Enter the name of a new friend:");
        String newName = scanner.nextLine();
        System.out.println("Enter the birthday of " + newName + " (YYYY-MM-DD):");
        String newBirthday = scanner.nextLine();
        friendManager.addFriend(newName, newBirthday);

        // Displaying the updated friends list
        friendManager.displayFriends();

    }
}
