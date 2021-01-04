Challenge:
```
mport java.util.Scanner;


public class SuperSecure {
  public static void main(String[] args) {
    Scanner in = new Scanner(System.in);
    String input = in.next();
    if(input.length() != 10) {
      System.out.println("LOL no");
      System.exit(0);
    }
    String changed = change(input);
    if(changed.equals("fvbl}bf334")) {
      System.out.println("Awesome!");
      System.out.println("The flag is: " + input);
    } else {
      System.out.println("LOL no");
    }
   }
   private static String change(String s) {
    char[] temp = new char[10];
    for(int i = 0; i < s.length(); i++) {
      temp[i] = (char)(s.charAt(i) + 3);
    }
    return new String(temp);
  }
}
```
If you did programming before it is very easy. The Java code is getting a input from the user which should be of length 10 and then calling the ```change()``` function
and passing the input provided as the argument. In the ```change()``` function it is simply modifing the input, it is taking every character of the input and changing the
letter to its concurrent 3rd letter i.e., ```A will become D``` i.e., A + 3 alphabet = D . After that it is comparing the returned string from the ```change()``` function
to ```fvbl}bf334```. So if we reverse the process of the ```change()``` function with the input ```fvbl}bf334``` we will get the flag. I wrote my own java code for this

Code:
```
import java.util.Scanner;

public class idk {

	public static void main(String[] args) {
	 	Scanner in = new Scanner(System.in);
    	System.out.println("Enter the text \n");
      String input = in.next();
    	char[] temp = new char[10];
    	for(int i = 0; i < input.length(); i++) {
      		temp[i] = (char)(input.charAt(i) - 3);
    	}
    	System.out.println(temp); 
	}

}
```
Output:
```
Enter the text 

fvbl}bf334
cs_iz_c001
```

We got our flag: ```cs_iz_c001```
