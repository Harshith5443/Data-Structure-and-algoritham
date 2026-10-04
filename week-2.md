
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


````
````markdown
