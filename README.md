//BufferedImageStack
//explanation
import java.awt.image.BufferedImage;
import java.util.EmptyStackException;
//Analeigh Wagner & Samhitha Bandi

public class BufferedImageStack {
    private BufferedImage[] stack; //the array to hold the stack elements
    private int top; //index of top element
    
    //new stack with an initial capacity of 2
    public BufferedImageStack() {
        stack=new BufferedImage[2];
        top=-1; //-1 - empty stack
    }
    
    //adds a mew image to the top of the stack
    //if the array is full it'll double the size before adding
    public void push(BufferedImage someBufferedImage) {
        //checking for more space
        if(top==stack.length-1) {
            BufferedImage[] newStack=new BufferedImage[stack.length*2];
            for(int i=0; i<=top; i++) {
                newStack[i]=stack[i];
            }
            stack=newStack;
        }
        //add image
        top++;
        stack[top]=someBufferedImage;
    }
    
    //remove and return the top image of the stack
    //throw emptystack exception
    public BufferedImage pop() {
        if(isEmpty()) {
            throw new EmptyStackException();
        }
        BufferedImage result=stack[top];
        stack[top]=null; //clear
        top--;
        return result;
    }
    
    //this returns true if theres nothing in the stack
    public boolean isEmpty() {
        return top==-1;
    }
    
    //this is for testing and gets the image at a specific position
    public BufferedImage get(int index) {
        if(index<0 || index>top) {
            throw new IndexOutOfBoundsException("This index "+index+" is out of bounds");
        }
        return stack[index];
    }
    
    // returns the no.of images currently in the stack
    public int getSize() {
        return top+1;
    }
    
    
    //this is for grading and returns the current capacity of the underlying array
    public int getArraySize() {
        return stack.length;
    }
}

