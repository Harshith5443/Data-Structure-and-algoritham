````markdown
# Recursion – Print 1 to 5

## Question 1

**Problem:**  
Write a Java program using recursion to print numbers from 1 to 5.

### Java Code

```java
public class P1 {

    public static void print(int i) {

        if (i <= 5) {
            System.out.println(i);
            print(i + 1);
        }
    }

    public static void main(String[] args) {
        print(1);
    }
}
```

### Sample Output

```text
1
2
3
4
5
```
````

````markdown
# Recursion – Sum of Given Number

## Question 2

**Problem:**  
Write a Java program using recursion to find the sum of numbers from 1 to the given number.

### Java Code

```java
public class P2 {

    static int sum(int no) {

        if (no == 1)
            return 1;

        return no + sum(no - 1);
    }

    public static void main(String[] args) {

        int n = 5;

        System.out.println("Sum : " + sum(n));
    }
}
```

### Sample Output

```text
Sum : 15
```
