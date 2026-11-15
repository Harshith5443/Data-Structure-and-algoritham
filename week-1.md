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


````
````markdown
# Recursion – Factorial of a Number

## Question 3

**Problem:**  
Write a Java program using recursion to find the factorial of a given number.

### Java Code

```java
public class P3 {

    static int factorial(int no) {

        if (no == 1)
            return 1;

        return no * factorial(no - 1);
    }

    public static void main(String[] args) {

        int n = 5;

        System.out.println("Factorial : " + factorial(n));
    }
}
```

### Sample Output

```text
Factorial : 120
```

````
````markdown
# Recursion – Fibonacci Series

## Question 4

**Problem:**  
Write a Java program using recursion to find the Fibonacci number at a given position.

### Java Code

```java
public class P4 {

    static int fib(int no) {

        if (no == 0)
            return 0;
        else if (no == 1 || no == 2)
            return 1;
        else
            return fib(no - 1) + fib(no - 2);
    }

    public static void main(String[] args) {

        int n = 5;

        System.out.println("Fibonacci : " + fib(n));
    }
}
```

### Sample Output

```text
Fibonacci : 5
```

````
````markdown
# Java Stream API Example

## Question

Write a Java program using the Stream API to filter even numbers, multiply them by 2, sort them, and print the result.

### Java Code

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class Example {
    public static void main(String[] args) {

        List<Integer> l1 = Arrays.asList(7, 5, 6, 8, 1, 4, 2);

        List<Integer> list = l1.stream()
                .filter((n) -> n % 2 == 0)
                .map((n) -> n * 2)
                .sorted()
                .collect(Collectors.toList());

        list.forEach((n) -> System.out.println(n));
    }
}
```

### Sample Output

```text
4
8
12
16
```

````
````markdown
# Comparable Interface – Sort Stations by Flouride

## Question

Write a Java program using the `Comparable` interface to sort the station objects based on their fluoride value.

### Java Code

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

class Station implements Comparable<Station> {

    String station_name;
    double temp;
    double ph;
    double chloride;
    double flouride;

    public Station(String station_name, double temp, double ph,
                   double chloride, double flouride) {
        super();
        this.station_name = station_name;
        this.temp = temp;
        this.ph = ph;
        this.chloride = chloride;
        this.flouride = flouride;
    }

    @Override
    public String toString() {
        return "Station [station_name=" + station_name
                + ", temp=" + temp
                + ", ph=" + ph
                + ", chloride=" + chloride
                + ", flouride=" + flouride + "]";
    }

    @Override
    public int compareTo(Station that) {
        return Double.compare(this.flouride, that.flouride);
    }
}

public class Mainclass {
    public static void main(String[] args) {

        List<Station> l1 = new ArrayList<Station>();

        l1.add(new Station("rampalli(hp)", 27.05, 7.20, 289.11, 1.22));
        l1.add(new Station("ethur(hp)", 27.62, 7.70, 286.35, 1.23));
        l1.add(new Station("edagaplli(hp)", 28.97, 7.89, 348.62, 0.81));
        l1.add(new Station("sugalmitta", 28.91, 8.02, 45.91, 0.82));
        l1.add(new Station("dandupalayam", 28.75, 8.10, 40.64, 0.55));
        l1.add(new Station("melapatla", 29.50, 7.40, 75.20, 1.71));
        l1.add(new Station("aradigunta", 29.82, 7.57, 80.50, 2.00));
        l1.add(new Station("bhemiganpalli", 29.67, 8.40, 88.12, 1.96));
        l1.add(new Station("bandlapalle", 28.70, 7.07, 156.01, 3.01));
        l1.add(new Station("mangalam", 28.96, 7.88, 124.98, 1.97));
        l1.add(new Station("melumododdi", 26.25, 7.40, 250.02, 1.01));
        l1.add(new Station("nekkondi", 29.85, 7.57, 232.84, 1.85));
        l1.add(new Station("palyampalle", 27.50, 8.40, 157.27, 1.97));
        l1.add(new Station("raganipalle", 28.60, 7.07, 98.58, 1.67);
        l1.add(new Station("vanamaladinne", 28.58, 7.88, 89.69, 1.46));
        l1.add(new Station("ns pet oh tank", 29.55, 7.20, 258.05, 1.38));
        l1.add(new Station("gokul oh tank", 27.72, 7.70, 249.87, 1.22));
        l1.add(new Station("vbhs oh tank", 28.87, 7.89, 246.89, 1.25));
        l1.add(new Station("kk palyam (tw)", 29.85, 8.02, 236.25, 0.36));
        l1.add(new Station("kk street (tw)", 27.05, 8.10, 238.92, 0.48));
        l1.add(new Station("an kunta (bw)", 27.62, 7.40, 222.98, 1.22));
        l1.add(new Station("nakabanda(bw)", 28.97, 7.57, 224.95, 1.35));
        l1.add(new Station("gudur palli(bw)", 28.91, 8.40, 196.25, 1.17));
        l1.add(new Station("lakkunta(bw)", 28.75, 7.72, 187.25, 1.79));
        l1.add(new Station("dhobicolony(bw)", 29.50, 7.40, 211.96, 1.58));
        l1.add(new Station("ng palyam (bw)", 29.82, 7.57, 210.02, 1.76));
        l1.add(new Station("hs street (bw)", 29.67, 8.40, 208.52, 1.82));
        l1.add(new Station("bodevaripalle(bw)", 28.70, 7.07, 196.26, 1.95));
        l1.add(new Station("chadalla (bw)", 28.96, 7.88, 190.29, 1.42));
        l1.add(new Station("etavakaili (bw)", 27.02, 8.20, 198.43, 1.14));

        Collections.sort(l1);

        l1.forEach(System.out::println);
    }
}
```

### Sample Output

```text
Station [station_name=kk palyam (tw), temp=29.85, ph=8.02, chloride=236.25, flouride=0.36]
Station [station_name=kk street (tw), temp=27.05, ph=8.10, chloride=238.92, flouride=0.48]
Station [station_name=dandupalayam, temp=28.75, ph=8.1, chloride=40.64, flouride=0.55]
Station [station_name=edagaplli(hp), temp=28.97, ph=7.89, chloride=348.62, flouride=0.81]
Station [station_name=sugalmitta, temp=28.91, ph=8.02, chloride=45.91, flouride=0.82]
...
Station [station_name=bandlapalle, temp=28.7, ph=7.07, chloride=156.01, flouride=3.01]
```

````
````markdown
# Comparator – Sort Stations by Fluoride

## Question

Write a Java program using `Comparator` to sort station objects based on their fluoride value.

### Java Code

```java
package comparator;

import java.util.ArrayList;
import java.util.Comparator;
import java.util.List;

class Station {

    String station_name;
    double temp;
    double ph;
    double chloride;
    double flouride;

    public Station(String station_name, double temp, double ph,
                   double chloride, double flouride) {
        super();
        this.station_name = station_name;
        this.temp = temp;
        this.ph = ph;
        this.chloride = chloride;
        this.flouride = flouride;
    }

    @Override
    public String toString() {
        return "Station [station_name=" + station_name
                + ", temp=" + temp
                + ", ph=" + ph
                + ", chloride=" + chloride
                + ", flouride=" + flouride + "]";
    }
}

public class Mainclass {

    public static void main(String[] args) {

        Comparator<Station> com =
                (i, j) -> i.flouride > j.flouride ? 1 : -1;

        List<Station> l1 = new ArrayList<Station>();

        l1.add(new Station("rampalli(hp)", 27.05, 7.20, 289.11, 1.22));
        l1.add(new Station("ethur(hp)", 27.62, 7.70, 286.35, 1.23));
        l1.add(new Station("edagaplli(hp)", 28.97, 7.89, 348.62, 0.81));
        l1.add(new Station("sugalmitta", 28.91, 8.02, 45.91, 0.82));
        l1.add(new Station("dandupalayam", 28.75, 8.10, 40.64, 0.55));
        l1.add(new Station("melapatla", 29.50, 7.40, 75.20, 1.71));
        l1.add(new Station("aradigunta", 29.82, 7.57, 80.50, 2.00));
        l1.add(new Station("bhemiganpalli", 29.67, 8.40, 88.12, 1.96));
        l1.add(new Station("bandlapalle", 28.70, 7.07, 156.01, 3.01));
        l1.add(new Station("mangalam", 28.96, 7.88, 124.98, 1.97));
        l1.add(new Station("melumododdi", 26.25, 7.40, 250.02, 1.01));
        l1.add(new Station("nekkondi", 29.85, 7.57, 232.84, 1.85));
        l1.add(new Station("palyampalle", 27.50, 8.40, 157.27, 1.97));
        l1.add(new Station("raganipalle", 28.60, 7.07, 98.58, 1.67));
        l1.add(new Station("vanamaladinne", 28.58, 7.88, 89.69, 1.46));
        l1.add(new Station("ns pet oh tank", 29.55, 7.20, 258.05, 1.38));
        l1.add(new Station("gokul oh tank", 27.72, 7.70, 249.87, 1.22));
        l1.add(new Station("vbhs oh tank", 28.87, 7.89, 246.89, 1.25));
        l1.add(new Station("kk palyam (tw)", 29.85, 8.02, 236.25, 0.36));
        l1.add(new Station("kk street (tw)", 27.05, 8.10, 238.92, 0.48));
        l1.add(new Station("an kunta (bw)", 27.62, 7.40, 222.98, 1.22));
        l1.add(new Station("nakabanda(bw)", 28.97, 7.57, 224.95, 1.35));
        l1.add(new Station("gudur palli(bw)", 28.91, 8.40, 196.25, 1.17));
        l1.add(new Station("lakkunta(bw)", 28.75, 7.72, 187.25, 1.79));
        l1.add(new Station("dhobicolony(bw)", 29.50, 7.40, 211.96, 1.58));
        l1.add(new Station("ng palyam (bw)", 29.82, 7.57, 210.02, 1.76));
        l1.add(new Station("hs street (bw)", 29.67, 8.40, 208.52, 1.82));
        l1.add(new Station("bodevaripalle(bw)", 28.70, 7.07, 196.26, 1.95));
        l1.add(new Station("chadalla (bw)", 28.96, 7.88, 190.29, 1.42));
        l1.add(new Station("etavakaili (bw)", 27.02, 8.20, 198.43, 1.14));

        Collections.sort(l1, com);

        for (Station station : l1) {
            System.out.println(station);
        }
    }
}
```

### Sample Output

```text
Station [station_name=kk palyam (tw), temp=29.85, ph=8.02, chloride=236.25, flouride=0.36]
Station [station_name=kk street (tw), temp=27.05, ph=8.1, chloride=238.92, flouride=0.48]
Station [station_name=dandupalayam, temp=28.75, ph=8.1, chloride=40.64, flouride=0.55]
Station [station_name=edagaplli(hp), temp=28.97, ph=7.89, chloride=348.62, flouride=0.81]
Station [station_name=sugalmitta, temp=28.91, ph=8.02, chloride=45.91, flouride=0.82]
...
```

