//.........Shopping cart.............

import java.util.Scanner;
import java.util.Vector;
public class ShoppingCart
{
	Vector v1 = new Vector();
	Vector v2= new Vector();
	Vector v3 = new Vector();
	Vector v4 = new Vector();
	String iname;
	float icost, total;
	int quantity;
	int i = 0;
	int pos;
	
	public void choices()
	{
		int choice;
		Scanner s1=new Scanner(System.in);
		
		System.out.println("\n\n\n----------------------ENTER YOUR CHOICE---------------------\n\n\n");
		System.out.println("What Do You Want To Do?");
		System.out.println("1.Add To Cart");
		System.out.println("2.Remove From Cart");
		System.out.println("3.Show Cart");
		System.out.println("4.Checkout");
		System.out.println("5.Exit");
		
		choice=s1.nextInt();
		switch (choice) {
		case 1:
			add();
			break;
		case 2:
			
		if(i>0)
		{
			remove();
		}
		else
		{
			System.out.println("\n\n\n------------------Aughs!!Your Cart Is Empty-----------------");
			choices();
		}
			break;
	
		case 3:
			if(i>0)
			{
				show();
	}
			else
			{
				System.out.println("\n\n\n------------------Aughs!!Your Cart Is Empty-----------------");
				choices();
			}
					
			break;
		case 4:
			if(i>0)
			{
				cartTotal();
	}
			else
			{
				System.out.println("\n\n\n---------------------You Bought Nothing---------------------");
				choices();
			}
					
			break;
			
		case 5:
			System.out.println("Thank You!!!! Visit Once Again$$!!");
			break;
		default:
			System.out.println("Oops!! Incorrect Choice!! Try Again");
			break;
		}	
	}
	
	/*$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$
	  $$$$$$$$$$$$$$$$$$$$$$$$$$$ADDING THE ITEM TO CART $$$$$$$$$$$$$$$$$$$$$$$$$$$$        
	  $$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$*/
	
	public void add()
	{	System.out.println("\n\n\n----------------------------ADD-----------------------------\n\n\n");
	
	Scanner s = new Scanner(System.in);
	System.out.println("Enter the Name Of Item:");	
    iname=s.next();
    v1.add(i,iname);
    System.out.println("Enter the Price Of This Item:");	
    icost=s.nextInt();
    v2.add(i,icost);
    System.out.println("Enter the Quantiy Of This Item:");	
    quantity=s.nextInt();
    v3.add(i,quantity);
    total = quantity*icost;
    v4.add(i,total);
	i++;
	System.out.println("\n\n\n---------------------------ADDED----------------------------\n");
	
	choices();
	}
	
	/*$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$
	  $$$$$$$$$$$$$$$$$$$$$$$$$$$REMOVE THE ITEM FROM CART $$$$$$$$$$$$$$$$$$$$$$$$$$        
	  $$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$*/
	
	public void remove()
	{
		System.out.println("\n\n\n---------------------------REMOVE---------------------------\n\n\n");
			
		System.out.println("What is the position of the element you want to remove");
		Scanner s2 =new Scanner(System.in);
		pos=s2.nextInt();
		System.out.println("Removed Item is:"+v1.elementAt(pos));
		v1.remove(pos);
		v2.remove(pos);
		v3.remove(pos);
		v4.remove(pos);
		i--;
		System.out.println("\n\n\n---------------------------REMOVED--------------------------\n\n\n");
			
		choices();
	}	
	
	/*$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$
	  $$$$$$$$$$$$$$$$$$$$$$$$$$$SHOWING THE ITEM IN CART $$$$$$$$$$$$$$$$$$$$$$$$$$$        
	  $$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$*/
	
	public void show()
	{	System.out.println("\n\n\n||********************************************************||");
		System.out.println("||-----------------------YOUR CART------------------------||");
			System.out.println("||********************************************************||\n");	
		for(int j = 0;j<i;j++)
		{
				System.out.println("ITEM:        "+v1.elementAt(j));
				System.out.println("COST:        "+v2.elementAt(j)+".Rs");
				System.out.println("QUANTITY:    "+v3.elementAt(j));
				System.out.println("-----------------------------");
				System.out.println("TOTAL:       "+v4.elementAt(j)+".Rs");
				System.out.println("------------------------------");
		}
	
		choices();
		
	}

	/*$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$
	  $$$$$$$$$$$$$$$$$$$$$$$$$$$SHOWING THE ITEM IN CART $$$$$$$$$$$$$$$$$$$$$$$$$$$        
	  $$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$*/
	
		void cartTotal()
		{
			float cartt=0;
		
			for(int j = 0;j<i;j++)
			{
			cartt=(float) v4.elementAt(j)+cartt;	
			
			}
			System.out.println("||********************************************************||");
			System.out.println("||********************************************************||");
			System.out.println("||        You Have Done Shopping Of:"+cartt+".Rs               ||");
			System.out.println("||    Pay The Total To Our Programmer and Visit us Again  || ");
			System.out.println("||********************************************************||");
			System.out.println("||********************************************************||");
			
		}

	public static void main(String[] args) {
		
		System.out.println("||********************************************************||");
		System.out.println("||********************************************************||");
		System.out.println("||********************************************************||");
		System.out.println("||                                                        ||");
		System.out.println("||                        SHOP HERE                       ||");
		System.out.println("||                                                        ||");
		System.out.println("||********************************************************||");
		System.out.println("||********************************************************||");
		System.out.println("||********************************************************||");
		
		ShoppingCart obj = new ShoppingCart();
		
		obj.choices();
			}
	}
