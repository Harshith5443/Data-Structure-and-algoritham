
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


````
````markdown
# Stack

## Question 3

**Problem:**  
Write a Java program to implement a Stack using an array with the following operations:

- Creation
- Push
- Pop
- Peek
- Is Empty
- Is Full
- Display
- Delete Stack

### Java Code

```java
class Stack_prgam {

    int[] stack;
    int top;

    // Creation
    public void creation(int size) {

        stack = new int[size];
        top = -1;
    }

    // Check Empty
    public boolean isEmpty() {
        return top == -1;
    }

    // Check Full
    public boolean isFull() {
        return top == stack.length - 1;
    }

    // Push operation
    public void push(int value) {

        if (isFull()) {

            System.out.println("Stack is Full");

        } else {

            stack[++top] = value;
            System.out.println(value + " pushed into stack");
        }
    }

    // Pop operation
    public void pop() {

        if (isEmpty()) {

            System.out.println("Stack is Empty");

        } else {

            int data = stack[top];
            top--;

            System.out.println(data + " popped from stack");
        }
    }

    // Peek operation
    public void peek() {

        if (isEmpty()) {

            System.out.println("Stack is Empty");

        } else {

            System.out.println("Top element: " + stack[top]);
        }
    }

    // Delete Stack
    public void deleteStack() {

        stack = null;

        System.out.println("Stack deleted");
    }

    // Display operation
    public void display() {

        if (isEmpty()) {

            System.out.println("Stack is Empty");

        } else {

            System.out.println("Stack elements:");

            for (int i = top; i >= 0; i--) {
                System.out.println(stack[i]);
            }
        }
    }
}

public class Main {

    public static void main(String[] args) {

        Stack_prgam s = new Stack_prgam();

        s.creation(5);

        s.push(10);
        s.push(20);
        s.push(30);

        s.display();

        s.peek();

        s.pop();

        s.display();

        s.deleteStack();
    }
}
```

### Sample Output

```text
10 pushed into stack
20 pushed into stack
30 pushed into stack

Stack elements:
30
20
10

Top element: 30

30 popped from stack

Stack elements:
20
10

Stack deleted
```


````
````markdown
# Browser History Using Stack

## Question 4

**Problem:**  
Write a Java program to implement browser page navigation using two stacks for previous and next pages.

### Java Code

```java
import java.util.Stack;

class Web {

    private String currentPage;
    private Stack<String> bws;
    private Stack<String> fws;

    public Web() {

        bws = new Stack<String>();
        fws = new Stack<String>();

        this.currentPage = "Home Page";
    }

    // Visit New Page
    public void visitPage(String newPage) {

        bws.push(currentPage);
        currentPage = newPage;

        fws.clear();
    }

    // Previous Page
    public void previousPage() {

        if (!bws.isEmpty()) {

            fws.push(currentPage);
            currentPage = bws.pop();
        }
    }

    // Next Page
    public void nextPage() {

        if (!fws.isEmpty()) {

            bws.push(currentPage);
            currentPage = fws.pop();
        }
    }

    // Get Current Page
    public String getCurrentPage() {

        return currentPage;
    }
}

public class Web_MainClass {

    public static void main(String[] args) {

        Web web = new Web();

        web.visitPage("Flipkart");
        web.visitPage("Flipkart Home Page");
        web.visitPage("Rc Toys");

        web.previousPage();

        System.out.println(web.getCurrentPage());
    }
}


````
````markdown
# Queue

## Question 2

**Problem:**  
Write a Java program to implement a Queue using an array with the following operations:

- Creation
- Enqueue
- Dequeue
- Peek
- Is Empty
- Is Full
- Display
- Delete Queue

### Java Code

```java
package ds_pro;

class QueueOp {

    int[] queue;
    int front;
    int rear;

    // Creation
    QueueOp(int size) {

        queue = new int[size];

        front = -1;
        rear = -1;
    }

    // Check Full
    public boolean isFull() {

        return rear == queue.length - 1;
    }

    // Check Empty
    public boolean isEmpty() {

        return front == -1;
    }

    // Enqueue
    public void enqueue(int value) {

        if (isFull()) {

            System.out.println("Queue is Full");

        } else {

            if (rear == -1) {
                front = 0;
            }

            queue[++rear] = value;

            System.out.println(value + " inserted into queue");
        }
    }

    // Dequeue
    public void dequeue() {

        if (isEmpty()) {

            System.out.println("Queue is Empty");

        } else {

            int value = queue[front++];

            System.out.println(value + " deleted from queue");

            if (front > rear) {
                front = -1;
                rear = -1;
            }
        }
    }

    // Peek
    public void peek() {

        if (isEmpty()) {

            System.out.println("Queue is Empty");

        } else {

            System.out.println(
                "Front element: " + queue[front]
            );
        }
    }

    // Display
    public void display() {

        if (isEmpty()) {

            System.out.println("Queue is Empty");

        } else {

            System.out.println("Queue elements:");

            for (int i = front; i <= rear; i++) {
                System.out.println(queue[i]);
            }
        }
    }

    // Delete Queue
    public void deleteQueue() {

        queue = null;
        front = -1;
        rear = -1;

        System.out.println("Queue deleted");
    }

    public static void main(String[] args) {

        QueueOp q = new QueueOp(5);

        System.out.println(q.isFull());
        System.out.println(q.isEmpty());

        q.enqueue(10);
        q.enqueue(20);
        q.enqueue(30);

        q.display();

        q.peek();

        q.dequeue();

        q.display();

        q.deleteQueue();
    }
}
```

### Sample Output

```text
false
true
10 inserted into queue
20 inserted into queue
30 inserted into queue

Queue elements:
10
20
30

Front element: 10

10 deleted from queue

Queue elements:
20
30

Queue deleted
```

````
````markdown


````
````markdown


````
````markdown


````
````markdown
