

import java.util.Scanner;
import java.util.Arrays;
public class Main
{
public static	int [] listofFactors(int n)
	{
		int [] factor=new int[n];
		int indx=0;
		for(int i=1;i*i<=n;i++)
		{
			if(n%i==0)
			{    
				factor[indx]=i;
				indx++;
				if(n/i!=i)
				{
					
					factor[indx]=n/i;
					indx++;
				}
			}
		}
		return Arrays.copyOfRange(factor,0,indx);
	}
	public static void main (String[] args)
	{
		
		Scanner sc=new Scanner(System.in);
	int n=sc.nextInt();
		int [] factors=listofFactors(n);
		Arrays.sort(factors);
		System.out.print("{"+factors[0]);
		for(int i=1;i<factors.length;i++)
		{
			System.out.print(","+factors[i]);
		}
		System.out.print("}");
	}
}
