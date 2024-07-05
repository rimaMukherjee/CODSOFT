import java.util.Scanner;
import java.util.Random;

public class NumberGame{
    public static void main(String[] args){
        Scanner sc= new Scanner(System.in);
        Random r= new Random();
        boolean tryAgain=true;
        int Score=0;

        while(tryAgain){
            int GuessingNum=r.nextInt(100);
            int maxTrial=7;
            boolean Success=false;

            System.out.println("Let's start the game!");
            System.out.println("Guess the number between 1-100");

            for(int trial=1;trial<=maxTrial;trial++){
                System.out.println("Enter your guessing no.");
                System.out.println("Attempt"+trial+"/"+maxTrial);
                int EnteredNum=sc.nextInt();

                if(EnteredNum==GuessingNum){
                    Success=true;
                    Score++;
                    System.out.println("WOW! guessed no. is correct");
                    break;
                }
                else if(EnteredNum<GuessingNum){
                    System.out.println("Too low! Enter again");
                }
                else{
                    System.out.println("Too High! Enter again");
                }
            }
            if(!Success){
                System.out.println("Sorry! All trials has ended....");
                System.out.println("The correct no.:"+GuessingNum);
            }
            System.out.println("Recent Score:"+Score);
            System.out.println("Wanna play again?(YES/NO):");
            tryAgain=sc.next().equalsIgnoreCase("yes");
            System.out.println("A new round has started!");
        }
        System.out.println("Thank you for playing!");
        System.out.println("Your final score is:"+Score);
        sc.close();
    }
}
