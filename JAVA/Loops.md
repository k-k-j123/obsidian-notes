Again the syntax is same as that of C

### While:
```
while(condition){
	//code;
}
```

### For:
```
for(initialization;condition;updation){
//code;
}
```

### Do While:
```
do{
	//code;
}while(condition)
```


> [!NOTE] Difference between While and Do while loop:
> Do while executes code once irrespective of the condition being true or false Whereas while only executes code inside it if condition is True



### Code example:
Sum of first n natural no:
```
import java.util.*;

class Main {
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    System.out.println("enter range:");
    int n = sc.nextInt();
    int counter = 1;
    int sum = 0;
    while (counter <= n) {
      sum += counter;
      counter++;
    }
    System.out.println("sum is " + sum);
    sc.close();
  }
}
```

pattern Program:
```
class Main {
  public static void main(String[] args) {
    int i,j;
    for(i=0;i<5;i++){
      for(j=0;j<=i;j++){
        System.out.print("* ");
      }
      System.out.print("\n");
    }
  }
}
prints 
*
**
***
****
*****
```

