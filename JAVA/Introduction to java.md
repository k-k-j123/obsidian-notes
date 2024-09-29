
Java is an object oriented programming language 
Its environment consist of jdk which has jre which has jvm 

## Java Hello world
```
class HelloWorld {
    public static void main(String args[])
    {
        System.out.println("Hello, World");
    }
}
```

there is a difference between print and println : println always prints on new line whereas print prints on the same line or you can use '\n' 
## Variables
```
class Veriables{
	public static void main(Strings args[])
	{
		int age=27;
		System.out.println("I am "+ age+" years old");
	}
}
```


## inputs
To take inputs in java we use scanner class but first we have to import it through import java.util.* ;
next we create an object of scanner class as `Scanner sc=new Scanner(System.in)` 
now to take input `sc.next()` 
```
import java.util.*;
public class Main{
  public static void main(String args[]){
    Scanner sc= new Scanner(System.in);
    String input=sc.next();
    System.out.println(input);
    sc.close();
  }
}
```

however the `sc.next()` will only capture till next line

here is the list of different types of scanner functions and their uses
Certainly! Here are different types of Java `Scanner` functions and their uses in one line each:

1. **nextLine()**: Reads a complete line of text. until next line
2. **next()**: Reads the next token from the input as a string. until next work 
3. **nextInt()**: Reads the next token as an integer. 
4. **nextDouble()**: Reads the next token as a double.
5. **nextBoolean()**: Reads the next token as a boolean.
6. **nextFloat()**: Reads the next token as a float.
7. **nextLong()**: Reads the next token as a long integer.
8. **nextShort()**: Reads the next token as a short integer.
9. **nextByte()**: Reads the next token as a byte.
10. **nextBigInteger()**: Reads the next token as a BigInteger.
11. **nextBigDecimal()**: Reads the next token as a BigDecimal.
12. **hasNext()**: Checks if there is another token in the input.
13. **hasNextInt()**: Checks if the next token can be interpreted as an integer.
14. **hasNextDouble()**: Checks if the next token can be interpreted as a double.
15. **hasNextBoolean()**: Checks if the next token can be interpreted as a boolean.
16. **hasNextFloat()**: Checks if the next token can be interpreted as a float.
17. **hasNextLong()**: Checks if the next token can be interpreted as a long integer.
18. **hasNextShort()**: Checks if the next token can be interpreted as a short integer.
19. **hasNextByte()**: Checks if the next token can be interpreted as a byte.


**example code: mathematical operations**
```
import java.util.*;
public class math_ops {
    public static void main(String args[]){
        Scanner sc=new Scanner(System.in);
        System.out.println("enter the value of a");
        int a=sc.nextInt();
        System.out.println("enter the value of b");
        int b=sc.nextInt();
        int sum=a+b;
        int sub=a-b;
        int mul=a*b;
        int div=a/b;
        System.out.println("the addition of " +a+" and "+ b +" is " + sum );
        System.out.println("the substraction of " +a+" and "+ b +" is " + sub );
        System.out.println("the multiplication of " +a+" and "+ b +" is " + mul );
        System.out.println("the division of " +a+" and "+ b +" is " + div );
        sc.close();
        
    }
}
```

## Type Conversion:


For Type Conversion two conditions must be satisfies:
1. The types must be Compatible that is you cannot store an string inside a int and so on
2. the size of destination type must be bigger than or equal to source type
byte -> short -> int -> float -> long -> double
here you can convert int to float or long but you cannot convert long to int 
This type of conversion is automatically done by java 
```
int a=5
long b=a //this is allowed and is called by widening conversion

long a=5
int b=a //this is not allowed and is called as lossy conversion
```


## Type Casting:
If you still want to perform a conversion irrespective of data loss or convert a character to number we use type casting

For example :
```
float num1=1999.999f;
int num2= (int) num1;
//here nums after decimal are removed and converted to int

char ch='a';
int char=(int) ch;
//this will store the ascii value of character 'a'
```

## Type Promotion:
Java when executing an instruction automatically converts all the data types of the variables of the expression to the data type which has largest size in that expression

for example : a is int, b is float, c is long then d=a+b+c is performed then d is a long type and a and b are converted to long data type during expression evaluation.

byte short char are converted to int and then solved
```
char a='a';
short b='50';
int sum =a+b
//char is converted to int i.e ascii value and b is converted to int
sum is 97 + 50

simillarly 
char a='a'
char b='b'
b-a will lead to 1
```
