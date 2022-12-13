package practice;
import java.util.*;
public class sirExample 
{
	public static void main(String[] args)
	{
		Scanner Scan = new Scanner(System.in);
			Random random = new Random();
			String myCharacterName, playerMove = "", enemyMove;
			int myHealth = 10, enemyHealth = 10;
			int mySP =0, enemySP = 0, round = 1;
			int mySPC, requirements;
			ArrayList<String> actions = new ArrayList<String>();
			ArrayList<String> enemyActions = new ArrayList<String>();
			System.out.println("Enter your username:");
			myCharacterName = Scan.nextLine();
			System.out.println("\nWelcome " + myCharacterName + "!\n");
			actions.clear();
			enemyActions.clear();
			do
			{
				skillsAvailable(mySP, actions);
			do
			{
				System.out.println("Input your action:");
				playerMove = Scan.nextLine();
				System.out.println("");
				requirements = mySPC (playerMove, actions);
				System.out.println(myCharacterName + "'s" + " move: " + playerMove);	
			}while (requirements == 1);
				enemySkillsAvailable(enemySP, enemyActions);
				int enemyPickedActions = random.nextInt(enemyActions.size());
				enemyMove = enemyActions.get(enemyPickedActions);
				System.out.println("Enemy's counter: " + enemyMove);
				System.out.println("");
				if(playerMove.equalsIgnoreCase("Charge"))
			{
				if(enemyMove.equalsIgnoreCase("Charge"))
				{
					mySP++;
					enemySP++;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Wave"))
				{
					mySP++;
					enemySP-=1;
					myHealth-=2;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Shield"))
				{
					mySP++;
					enemySP-=1;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Ax"))
				{
					mySP++;
					enemySP-=2;
					myHealth-=3;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Kamekameha"))
				{
					mySP++;
					enemySP-=4;
					myHealth-=6;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Amen"))
				{
					mySP++;
					enemySP-=5;
					enemyHealth+=5;
					round++;
				}
			}
			if(playerMove.equalsIgnoreCase("Shield"))
			{
				if(enemyMove.equalsIgnoreCase("Charge"))
				{
					mySP-=1;
					enemySP++;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Wave"))
				{
					mySP-=1;
					enemySP-=1;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Shield"))
				{
					mySP-=1;
					enemySP-=1;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Ax"))
				{
					mySP-=1;
					enemySP-=2;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Kamekameha"))
				{
					mySP-=1;
					enemySP-=4;
					myHealth-=6;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Amen"))
				{
					mySP-=1;
					enemySP-=5;
					enemyHealth+=5;
					round++;
				}
			}
			if(playerMove.equalsIgnoreCase("Ax"))
			{
				if(enemyMove.equalsIgnoreCase("Charge"))
				{
					mySP-=2;
					enemySP++;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Wave"))
				{
					mySP-=2;
					enemySP-=1;
					enemyHealth-=1;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Shield"))
				{
					mySP-=2;
					enemySP-=1;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Ax"))
				{
					mySP-=2;
					enemySP-=2;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Kamekameha"))
				{
					mySP-=2;
					enemySP-=4;
					myHealth-=3;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Amen"))
				{
					mySP-=2;
					enemySP-=5;
					enemyHealth+=5;
					round++;
				}
			}
			if(playerMove.equalsIgnoreCase("Kamekameha"))
			{
				if(enemyMove.equalsIgnoreCase("Charge"))
				{
					mySP-=4;
					enemySP++;
					enemyHealth-=6;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Wave"))
				{
					mySP-=4;
					enemySP-=1;
					enemyHealth-=4;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Shield"))
				{
					mySP-=4;
					enemySP-=1;
					enemyHealth-=6;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Ax"))
				{
					mySP-=4;
					enemySP-=2;
					enemyHealth-=3;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Kamekameha"))
				{
					mySP-=4;
					enemySP-=4;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Amen"))
				{
					mySP-=4;
					enemySP-=5;
					enemyHealth+=5;
					round++;
				}
			}
			if(playerMove.equalsIgnoreCase("Amen"))
			{
				if(enemyMove.equalsIgnoreCase("Charge"))
				{
					mySP-=5;
					enemySP++;
					myHealth+=5;
					round++;
				}
				
				if(enemyMove.equalsIgnoreCase("Wave"))
				{
					mySP-=5;
					enemySP-=1;
					myHealth+=5;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Shield"))
				{
					mySP-=5;
					enemySP-=1;
					myHealth+=5;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Ax"))
				{
					mySP-=5;
					enemySP-=2;
					myHealth+=5;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Kamekameha"))
				{
					mySP-=5;
					myHealth+=5;
					round++;
				}
				if(enemyMove.equalsIgnoreCase("Amen"))
				{
					mySP-=5;
					enemySP-=5;
					myHealth+=5;
					enemyHealth+=5;
					round++;
				}
			}
			if (myHealth <= 0)
			{
				myHealth = 0;
			}
			if (enemyHealth <= 0)
			{
				enemyHealth = 0;
			}
			actions.clear();
			enemyActions.clear();
			DisplayPlayerStats( myCharacterName, mySP, enemySP, round,  myHealth, enemyHealth);
			}while (!(myHealth <= 0 || enemyHealth <= 0));
			if (enemyHealth <= 0 )
			{
				displayWinningMoment(myCharacterName, round);
			}
			else
			{
				System.out.println("I'm sorry" + myCharacterName + "you lose!");
			}
		}
	public static void DisplayPlayerStats(String myCharacterName, int mySP, int enemySP, int round, int myHealth, int enemyHealth)
	{	
		String upperCaseName = (myCharacterName.toUpperCase());
		String myHealthStats = Integer.toString(myHealth);		
		String enemyHealthStats = Integer.toString(enemyHealth);
		String playerStat = "mySP: " + mySP + "\t\tuserName:" + upperCaseName + "\t\tmyHeath: " + myHealthStats
							+ "\nenemySP: " + enemySP + "\tRound:" + round + "\t\t\tenemyHealth: " + enemyHealthStats;
		System.out.println(playerStat);
		System.out.println("");
	}
	public static void displayWinningMoment(String myCharacterName, int round)
	{
		String upperCaseName = (myCharacterName.toUpperCase());
		String endRound = Integer.toString(round);
		String winMove = upperCaseName + " you won after " + endRound + " round!";
		System.out.println(winMove);
		System.out.println("");
	}
	public static void skillsAvailable(int mySP, ArrayList<String> actions) 
	{
		if (mySP >= 0)
		{
			actions.add("Charge");
		}
		if (mySP >= 1)
		{
			actions.add("Shield");
			actions.add("Wave");
		}
		if (mySP >= 2)
		{
			actions.add("Ax");
		}
		if (mySP >= 4)
		{
			actions.add("Kamekameha");
		}
		if (mySP >= 5)
		{
			actions.add("Amen");
		}
		System.out.println(actions);
	}
	
	public static void enemySkillsAvailable(int enemySP, ArrayList<String> enemyActions)
	{
		if (enemySP >= 0)
		{
			enemyActions.add("Charge");
		}
		
		if (enemySP >= 1)
		{
			enemyActions.add("Shield");
			enemyActions.add("Wave");
		}
		
		if (enemySP >= 2)
		{
			enemyActions.add("Ax");
		}
		
		if (enemySP >= 4)
		{
			enemyActions.add("Kamekameha");
		}
		if (enemySP >= 5)
		{
			enemyActions.add("Amen");
		}
		System.out.println(enemyActions);
	}
	public static int mySPC (String playerMove,ArrayList<String> actions)
	{
	int requirements = 0; 
	if(!(actions.contains("Shield")))
	{
		if(playerMove.equalsIgnoreCase("Shield"))
		{
			System.err.println("!!!Skill points not yet sufficient!!!");
			System.err.println("skill didn't proceed, pick again:");
			requirements = 1;
		}
	}
	if(!(actions.contains("Wave")))
	{
		if(playerMove.equalsIgnoreCase("Wave"))
		{
			System.err.println("!!!Skill points not yet sufficient!!!");
			System.err.println("skill didn't proceed, pick again:");
			requirements = 1;
		}
	}
	if(!(actions.contains("Ax")))
	{
		if(playerMove.equalsIgnoreCase("Ax"))
		{
			System.err.println("!!!Skill points not yet sufficient!!!");
			System.err.println("skill didn't proceed, pick again:");
			requirements = 1;
		}
	}
	if(!(actions.contains("Kamekameha")))
	{
		if(playerMove.equalsIgnoreCase("Kamekameha"))
		{
			System.err.println("!!!Skill points not yet sufficient!!!");
			System.err.println("skill didn't proceed, pick again:");
			requirements = 1;
		}
	}
	if(!(actions.contains("Amen")))
	{
		if(playerMove.equalsIgnoreCase("Amen"))
		{
			System.err.println("!!!Skill points not yet sufficient!!!");
			System.err.println("skill didn't proceed, pick again:");
			requirements = 1;
		}
	}
	return requirements;
}
}
