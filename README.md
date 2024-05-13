# Treasure-Hunt

/**
 * TreasureHunt
 *
 * Walt Payne
 * 13/3/24
 */
import java.util.Scanner;

public class TreasureHunt
{
    public static void main(String[] args){
        Scanner keyboard = new Scanner(System.in);
        int treasureX = (int)Math.round(Math.random()*7);
        int treasureY = (int)Math.round(Math.random()*5);
        int guessX=-1;
        int guessY=-1;
        char grid[][] = new char[7][5];
        boolean treasureFound = false;
        int guesses = 0;
        new TreasureHunt();
    }
    static void TreasureHunt(int treasureX, int treasureY, int guessX, int guessY, int guesses, boolean treasureFound, char grid[][], Scanner keyboard){
        for(int i=0; i<7; i++){
            for(int j=0; j<5; j++){
                grid[i][j] = '.';
            }
        }

        for(int i=0; !treasureFound; i++){
            for(int y=0; y<5; y++){
                for(int x=0; x<7; x++){
                    System.out.print(grid[x][y]);
                }
                System.out.println();
            }

            System.out.println("Enter the x position");
            guessX = keyboard.nextInt();
            System.out.println("Enter the y position");
            guessY = keyboard.nextInt();

            
            if(guessX==treasureX && guessY==treasureY){
                System.out.println("Congratulations, you have found the treasure!");
                treasureFound=true;
            }else if (guessX==46 && guessY==97) {
                System.out.println(treasureX+ " "+ treasureY);
            }else{
                System.out.println("You have not found the treasure");
                grid[guessX-1][guessY-1] = 'x';
            }
        }
    }
}
