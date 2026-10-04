
````markdown
# 1D Array – Single Dimension Array

## Question 1

**Problem:**  
Write a Java program to implement a single-dimensional array with the following operations:

- Create Array
- Insert
- Traversal
- Search by Value
- Search by Index
- Delete by Index
- Delete by Value
- Delete Entire Array

### Java Code

```java
package ds_pro;

public class SingleDimension {

    int[] a;

    // Create Array
    public SingleDimension(int size) {

        a = new int[size];

        for (int i = 0; i < a.length; i++) {
            a[i] = Integer.MIN_VALUE;
        }

        System.out.println("Array is Created");
    }

    // Insert
    public void insert(int index, int value) {

        try {
            if (a[index] == Integer.MIN_VALUE) {

                a[index] = value;
                System.out.println("The Value is Inserted");

            } else {
                System.out.println("Element already Exists");
            }

        } catch (ArrayIndexOutOfBoundsException e) {

            System.out.println("Invalid Index");
        }
    }

    // Traversal
    public void traversal() {

        for (int i = 0; i < a.length; i++) {
            System.out.println(a[i]);
        }
    }

    // Search by Value
    public void search(int value) {

        for (int i = 0; i < a.length; i++) {

            if (a[i] == value) {

                System.out.println(
                    "The element is found at index: " + i
                );

                return;
            }
        }

        System.out.println("The value is not Found");
    }

    // Search by Index
    public void search_BY_Index(int index) {

        try {
            if (a[index] != Integer.MIN_VALUE) {

                System.out.println(
                    "The value present at that index is: " + a[index]
                );

            } else {

                System.out.println("The index Value is Empty");
            }

        } catch (Exception e) {

            System.out.println("Invalid Index");
        }
    }

    // Delete by Index
    public void del_By_index(int index) {

        try {
            if (a[index] != Integer.MIN_VALUE) {

                a[index] = Integer.MIN_VALUE;

                System.out.println(
                    "The value deleted at index: " + index
                );

            } else {

                System.out.println("The value is empty");
            }

        } catch (Exception e) {

            System.out.println("Invalid Index");
        }
    }

    // Delete by Value
    public void deleteByValue(int value) {

        for (int i = 0; i < a.length; i++) {

            if (a[i] == value) {

                a[i] = Integer.MIN_VALUE;

                System.out.println("The value got deleted");

                return;
            }
        }

        System.out.println("The value is not Found");
    }

    // Delete Entire Array
    public void delete() {

        a = null;

        System.out.println("Array Got Deleted");
    }

    // Main Method
    public static void main(String[] args) {

        SingleDimension arr = new SingleDimension(5);

        arr.insert(0, 10);
        arr.insert(1, 20);
        arr.insert(2, 30);
        arr.insert(3, 40);
        arr.insert(4, 50);

        System.out.println("\nArray Elements:");
        arr.traversal();

        System.out.println("\nSearch:");
        arr.search(30);

        System.out.println("\nDelete By Value:");
        arr.deleteByValue(30);

        System.out.println("\nArray After Delete:");
        arr.traversal();

        System.out.println("\nDelete By Index:");
        arr.del_By_index(2);

        System.out.println("\nSearch By Index:");
        arr.search_BY_Index(3);

        System.out.println("\nDelete Entire Array:");
        arr.delete();
    }
}
```

### Sample Output

```text
Array is Created
The Value is Inserted
The Value is Inserted
The Value is Inserted
The Value is Inserted
The Value is Inserted

Array Elements:
10
20
30
40
50

Search:
The element is found at index: 2

Delete By Value:
The value got deleted

Array After Delete:
10
20
-2147483648
40
50

Delete By Index:
The value is empty

Search By Index:
The value present at that index is: 40

Delete Entire Array:
Array Got Deleted
```

````
````markdown
# 1D Array Using Object

## Question 2

**Problem:**  
Write a Java program to implement a one-dimensional array using `String` objects with the following operations:

- Create Array
- Insert
- Traversal
- Search by Value
- Search by Index
- Delete by Index
- Delete by Value
- Delete Entire Array

### Java Code

```java
public class SingelDO {

    String[] a;

    // Create Array
    public SingelDO(int size) {

        a = new String[size];

        System.out.println("Array is Created");
    }

    // Insert
    public void insert(int index, String value) {

        try {

            if (a[index] == null) {

                a[index] = value;
                System.out.println("The Value is Inserted");

            } else {

                System.out.println("Element already Exists");
            }

        } catch (ArrayIndexOutOfBoundsException e) {

            System.out.println("Invalid Index");
        }
    }

    // Traversal
    public void traversal() {

        for (int i = 0; i < a.length; i++) {

            System.out.println(a[i]);
        }
    }

    // Search by Value
    public void search(String value) {

        for (int i = 0; i < a.length; i++) {

            if (a[i] != null && a[i].equals(value)) {

                System.out.println(
                    "The element is found at index: " + i
                );

                return;
            }
        }

        System.out.println("The value is not Found");
    }

    // Search By Index
    public void search_BY_Index(int index) {

        try {

            if (a[index] != null) {

                System.out.println(
                    "The value present at that index is: " + a[index]
                );

            } else {

                System.out.println("The index value is Empty");
            }

        } catch (ArrayIndexOutOfBoundsException e) {

            System.out.println("Invalid Index");
        }
    }

    // Delete By Index
    public void del_By_index(int index) {

        try {

            if (a[index] != null) {

                a[index] = null;

                System.out.println(
                    "The value deleted at index: " + index
                );

            } else {

                System.out.println("The index is empty");
            }

        } catch (ArrayIndexOutOfBoundsException e) {

            System.out.println("Invalid Index");
        }
    }

    // Delete by Value
    public void deleteByValue(String value) {

        for (int i = 0; i < a.length; i++) {

            if (a[i] != null && a[i].equals(value)) {

                a[i] = null;

                System.out.println("The value got deleted");

                return;
            }
        }

        System.out.println("The value is not Found");
    }

    // Delete Entire Array
    public void delete() {

        a = null;

        System.out.println("Array Got Deleted");
    }

    // Main Method
    public static void main(String[] args) {

        SingelDO arr = new SingelDO(5);

        arr.insert(0, "Apple");
        arr.insert(1, "Banana");
        arr.insert(2, "Mango");
        arr.insert(3, "Orange");
        arr.insert(4, "Grapes");

        System.out.println("\nArray Elements:");
        arr.traversal();

        System.out.println("\nSearch:");
        arr.search("Mango");

        System.out.println("\nDelete:");
        arr.deleteByValue("Mango");

        System.out.println("\nArray After Delete:");
        arr.traversal();

        System.out.println("\nDelete By Index:");
        arr.del_By_index(2);

        System.out.println("\nSearch By Index:");
        arr.search_BY_Index(3);

        System.out.println("\nDelete Entire Array:");
        arr.delete();
    }
}
```

### Sample Output

```text
Array is Created
The Value is Inserted
The Value is Inserted
The Value is Inserted
The Value is Inserted
The Value is Inserted

Array Elements:
Apple
Banana
Mango
Orange
Grapes

Search:
The element is found at index: 2

Delete:
The value got deleted

Array After Delete:
Apple
Banana
null
Orange
Grapes

Delete By Index:
The index is empty

Search By Index:
The value present at that index is: Orange

Delete Entire Array:
Array Got Deleted
```


````
````markdown
# 2D Array – Two Dimensional Array

## Question 3

**Problem:**  
Write a Java program to implement a two-dimensional array with the following operations:

- Create 2D Array
- Insertion
- Search by Value
- Delete by Value
- Search by Index
- Delete by Index
- Traversal

### Java Code

```java
class TDA {

    int[][] arr;

    // Create 2D Array
    public TDA(int rsize, int csize) {

        arr = new int[rsize][csize];

        for (int row = 0; row < arr.length; row++) {
            for (int col = 0; col < arr[row].length; col++) {
                arr[row][col] = Integer.MIN_VALUE;
            }
        }
    }

    // INSERTION
    public void insertion(int row, int col, int value) {

        try {

            if (arr[row][col] == Integer.MIN_VALUE) {

                arr[row][col] = value;

                System.out.println("Value " + value + " inserted");

            } else {

                System.out.println("The cell is already filled");
            }

        } catch (Exception e) {

            System.out.println("Invalid row and col");
        }
    }

    // SEARCH BY VALUE
    public void search_By_Value(int search_Value) {

        for (int row = 0; row < arr.length; row++) {

            for (int col = 0; col < arr[row].length; col++) {

                if (arr[row][col] == search_Value) {

                    System.out.println(
                        "The value is present at index: "
                        + row + " : " + col
                    );

                    return;
                }
            }
        }

        System.out.println("The value is not present");
    }

    // DELETE BY VALUE
    public void delete_By_Value(int search_Value) {

        for (int row = 0; row < arr.length; row++) {

            for (int col = 0; col < arr[row].length; col++) {

                if (arr[row][col] == search_Value) {

                    arr[row][col] = Integer.MIN_VALUE;

                    System.out.println(
                        "Value " + search_Value + " deleted"
                    );

                    return;
                }
            }
        }

        System.out.println("The value is not present");
    }

    // SEARCH BY INDEX
    public void search_By_Index(int row, int col) {

        try {

            if (arr[row][col] != Integer.MIN_VALUE) {

                System.out.println(
                    "The value at index " + row + " : " + col
                    + " is " + arr[row][col]
                );

            } else {

                System.out.println("The cell is empty");
            }

        } catch (Exception e) {

            System.out.println("Invalid row and col");
        }
    }

    // DELETE BY INDEX
    public void delete_By_Index(int row, int col) {

        try {

            if (arr[row][col] != Integer.MIN_VALUE) {

                System.out.println(
                    "Value " + arr[row][col]
                    + " deleted from index "
                    + row + " : " + col
                );

                arr[row][col] = Integer.MIN_VALUE;

            } else {

                System.out.println("The cell is already empty");
            }

        } catch (Exception e) {

            System.out.println("Invalid row and col");
        }
    }

    // TRAVERSE
    public void traverse() {

        for (int row = 0; row < arr.length; row++) {

            for (int col = 0; col < arr[row].length; col++) {

                System.out.print(arr[row][col] + " ");
            }

            System.out.println();
        }
    }
}

public class MainClass {

    public static void main(String[] args) {

        TDA tda = new TDA(3, 3);

        // INSERTION
        tda.insertion(0, 0, 10);
        tda.insertion(0, 1, 20);
        tda.insertion(0, 2, 30);

        tda.insertion(1, 0, 40);
        tda.insertion(1, 1, 50);
        tda.insertion(1, 2, 60);

        tda.insertion(2, 0, 70);
        tda.insertion(2, 1, 80);
        tda.insertion(2, 2, 90);

        // INSERTING INTO ALREADY FILLED CELL
        tda.insertion(1, 1, 100);

        // SEARCH BY VALUE
        tda.search_By_Value(80);

        // DELETE BY VALUE
        tda.delete_By_Value(80);

        // SEARCH BY INDEX
        tda.search_By_Index(1, 1);

        // DELETE BY INDEX
        tda.delete_By_Index(1, 1);

        // TRAVERSE
        tda.traverse();
    }
}
```

### Sample Output

```text
Value 10 inserted
Value 20 inserted
Value 30 inserted
Value 40 inserted
Value 50 inserted
Value 60 inserted
Value 70 inserted
Value 80 inserted
Value 90 inserted
The cell is already filled
The value is present at index: 2 : 1
Value 80 deleted
The value at index 1 : 1 is 50
Value 50 deleted from index 1 : 1
10 20 30
40 -2147483648 60
70 -2147483648 90
```
