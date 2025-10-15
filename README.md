
import java.awt.image.BufferedImage;
//BufferedImageStack
//Analeigh Wagner & Samhitha Bandi
//explanation
public class BufferedImageStack {

	public static BufferedImage[] stack;
	public static int top;
	public static void BufferedImageStack() //implement stack of objects as an array and sets top
	{
		stack = new BufferedImage[2];
		top = -1;
	}
	
	
	public static void push(BufferedImage someBufferedImage)
	{
		if(getSize()==2)
		{
			stack= new BufferedImage[stack.length*2];
			for(int i=0; i<stack.length;i++)
			{
				stack[i] = stack[i];
			}
			stack[stack.length] = someBufferedImage;
		}
	}
	
	public static BufferedImage pop()   
	
	
	public static boolean isEmpty()
	{
		if(stack.length<1)
		{
			return true;
		}
		return false;
	}
	
	//public static -- get(int index)
	
	
	public static int getSize()
	{
		int count=0;
		for(int i=0; i<stack.length; i++)
		{
			if(stack[i]!=null)
			{
				count++;
			}
		}
		return count;
	}
	
	//public static int getArraySize()

}
