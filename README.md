Q2
==
import java.util.Scanner;


public class SmartPuzzleProgram {
	
	char[][] table = new char[5][5];
	
	public static void main(String[] args) {
		SmartPuzzleProgram obj = new SmartPuzzleProgram();
		//Start table with letters shown in the assignment.
		obj.table[0][0] = 'S';
		obj.table[0][1] = 'M';
		obj.table[0][2] = 'A';
		obj.table[0][3] = 'R';
		obj.table[0][4] = 'T';
		obj.table[1][1] = 'T';
		obj.table[1][2] = 'S';
		obj.table[1][3] = 'M';
		obj.table[2][2] = 'R';
		obj.table[2][4] = 'S';
		obj.table[3][1] = 'S';
		obj.table[3][2] = 'M';
		obj.table[4][2] = 'T';
		obj.table[4][3] = 'S';
		while(obj.gameOver() == false)
		{
			//Runs until game is over 
			obj.draw();
			obj.userInput();
			
		}
		System.out.println("Congratulations! You must be SMART.");
		
		
	}
	public boolean gameOver()
	{
		//Check if the table is complete
		int rows = 5;
		int colums = 5;
		int []sum = new int[5];
		for (int i = 0 ; i<rows; i++)
		{
			for (int j =0 ; j<colums; j++)
			{
		
				sum[i] += (int)table[i][j];
		
			}
		}
		if (sum[0] == sum[1] && sum[1] == sum[2] && sum[1] == sum[3] && sum[1] == sum[4] && sum[1] == 391)
		{
			return true;
		}
		return false;
	}
	public void userInput()
	{
		//Ask for user Input 
		Scanner sn = new Scanner(System.in);
		int row = 0;
		int column = 0;
		char letter = 'A';
		System.out.println("Enter a row (1-5):");
		row = sn.nextInt();
		System.out.println("Enter a column (1-5):");
		column = sn.nextInt();
		System.out.println("Enter a letter from (S,M,A,R or T): ");
		letter = sn.next().charAt(0);
		while(letter != 'S' && letter != 'M' && letter != 'A' && letter != 'R' && letter != 'T')
		{
			System.out.println("Invalid letter. Use 'S', M', 'A', 'R' or 'T'. ");
			letter = sn.next().charAt(0);
		}
		table[row-1][column-1] = letter;
	}
	public void draw()
	{
		//Draws the table
		int rows = 5;
		int colums = 5;
		System.out.println("   1   2   3   4   5");
		System.out.println("  ---+---+---+---+--- ");
		for (int i = 0 ; i<rows; i++)
		{
			
			System.out.print(i+1 +"|");
			for (int j =0 ; j<colums; j++)
			{
				System.out.print(" " +table[i][j] + " |");
			}
			System.out.println("");
			System.out.println("  ---+---+---+---+--- ");
			
		}
	}

}
