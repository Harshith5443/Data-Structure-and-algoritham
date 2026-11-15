````markdown
# Singly Linked List

## Question 1

**Problem:**  
Write a Java program to implement a Singly Linked List with the following operations:

1. Creation of a Singly Linked List
2. Insertion at a specific position
3. Forward Traversal
4. Backward Traversal
5. Reverse Linked List
6. Find Middle Node
7. Search an Element
8. Delete First Node
9. Delete Last Node
10. Delete at a Specific Position
11. Delete Entire Linked List
12. Display Size

### Java Code

```java
package linkedList;

class Node {
    int val;
    Node next;
}

class Single_LinkedList {

    Node head, tail;
    int size = 0;

    // Creation of Singly Linked List
    public void creationSLL(int data) {
        Node node = new Node();
        node.val = data;
        node.next = null;

        head = tail = node;
        size = 1;
    }

    // Insertion
    public void insertion(int loc, int value) {

        if (loc < 0) {
            System.out.println("Invalid location");
            return;
        }

        if (head == null) {
            if (loc == 0) {
                creationSLL(value);
            } else {
                System.out.println("Invalid location");
            }
            return;
        }

        Node node = new Node();
        node.val = value;

        if (loc == 0) {
            node.next = head;
            head = node;
        } else if (loc >= size) {
            node.next = null;
            tail.next = node;
            tail = node;
        } else {
            Node tempNode = head;

            for (int i = 0; i < loc - 1; i++) {
                tempNode = tempNode.next;
            }

            node.next = tempNode.next;
            tempNode.next = node;
        }

        size++;
    }

    // Forward Traversal
    public void fwdtraversal() {

        Node temp = head;

        while (temp != null) {
            System.out.print(temp.val + " -> ");
            temp = temp.next;
        }

        System.out.println("null");
    }

    // Backward Traversal
    public void bwdtraversal() {
        backward(head);
        System.out.println("null");
    }

    private void backward(Node node) {

        if (node == null) {
            return;
        }

        backward(node.next);
        System.out.print(node.val + " -> ");
    }

    // Reverse Linked List
    public void reverse() {

        Node prev = null;
        Node curr = head;

        tail = head;

        while (curr != null) {

            Node next = curr.next;
            curr.next = prev;

            prev = curr;
            curr = next;
        }

        head = prev;

        System.out.println("Linked List Reversed");
    }

    // Find Middle Node
    public void find_Mid() {

        if (head == null) {
            System.out.println("Linked List is empty");
            return;
        }

        Node fast = head;
        Node slow = head;

        while (fast != null && fast.next != null) {

            slow = slow.next;
            fast = fast.next.next;
        }

        System.out.println("Mid value is: " + slow.val);
    }

    // Search Element
    public void search(int data) {

        Node temp = head;

        while (temp != null) {

            if (data == temp.val) {
                System.out.println("The data is present");
                return;
            }

            temp = temp.next;
        }

        System.out.println("Data Not found");
    }

    // Delete First Node
    public void deleteFirst() {

        if (head == null) {
            System.out.println("Linked List is empty");
            return;
        }

        head = head.next;
        size--;

        if (head == null) {
            tail = null;
        }

        System.out.println("First node deleted");
    }

    // Delete Last Node
    public void deleteLast() {

        if (head == null) {
            System.out.println("Linked List is empty");
            return;
        }

        if (head == tail) {
            head = tail = null;
        } else {

            Node temp = head;

            while (temp.next != tail) {
                temp = temp.next;
            }

            temp.next = null;
            tail = temp;
        }

        size--;

        System.out.println("Last node deleted");
    }

    // Delete at Specific Position
    public void deleteAtPosition(int loc) {

        if (loc < 0 || loc >= size) {
            System.out.println("Invalid location");
            return;
        }

        if (loc == 0) {
            deleteFirst();
            return;
        }

        Node temp = head;

        for (int i = 0; i < loc - 1; i++) {
            temp = temp.next;
        }

        Node deleteNode = temp.next;
        temp.next = deleteNode.next;

        if (deleteNode == tail) {
            tail = temp;
        }

        size--;

        System.out.println("Node deleted at position " + loc);
    }

    // Delete Entire Linked List
    public void delete() {

        head = tail = null;
        size = 0;

        System.out.println("SLL is deleted");
    }

    // Display Size
    public void displaySize() {
        System.out.println("Size: " + size);
    }
}

public class MainClass {

    public static void main(String[] args) {

        Single_LinkedList sll = new Single_LinkedList();

        // Creation
        sll.creationSLL(10);

        // Insertion
        sll.insertion(1, 20);
        sll.insertion(2, 30);
        sll.insertion(3, 40);
        sll.insertion(2, 50);

        // Forward Traversal
        System.out.println("Forward Traversal:");
        sll.fwdtraversal();

        // Backward Traversal
        System.out.println("\nBackward Traversal:");
        sll.bwdtraversal();

        // Search
        System.out.println("\nSearching:");
        sll.search(40);

        // Find Middle
        System.out.println("\nFinding Middle:");
        sll.find_Mid();

        // Display Size
        sll.displaySize();

        // Reverse
        System.out.println("\nReverse Linked List:");
        sll.reverse();
        sll.fwdtraversal();

        // Delete First
        System.out.println("\nDelete First:");
        sll.deleteFirst();
        sll.fwdtraversal();

        // Delete Last
        System.out.println("\nDelete Last:");
        sll.deleteLast();
        sll.fwdtraversal();

        // Delete at Position
        System.out.println("\nDelete at Position:");
        sll.deleteAtPosition(1);
        sll.fwdtraversal();

        // Display Final Size
        sll.displaySize();

        // Delete Entire List
        sll.delete();
        sll.fwdtraversal();
    }
}
```

### Sample Output

```text
Forward Traversal:
10 -> 20 -> 50 -> 30 -> 40 -> null

Backward Traversal:
40 -> 30 -> 50 -> 20 -> 10 -> null

Searching:
The data is present

Finding Middle:
Mid value is: 50
Size: 5

Reverse Linked List:
Linked List Reversed
40 -> 30 -> 50 -> 20 -> 10 -> null

Delete First:
First node deleted
30 -> 50 -> 20 -> 10 -> null

Delete Last:
Last node deleted
30 -> 50 -> 20 -> null

Delete at Position:
Node deleted at position 1
30 -> 20 -> null
Size: 2

SLL is deleted
null
```

````
````markdown
# Doubly Linked List

## Question 2

**Problem:**  
Write a Java program to implement a Doubly Linked List with the following operations:

1. Creation of Doubly Linked List
2. Insertion at a specific position
3. Forward Traversal
4. Backward Traversal
5. Search an Element
6. Find Middle Node
7. Reverse Doubly Linked List
8. Delete First Node
9. Delete Last Node
10. Delete at a Specific Position
11. Delete Entire Doubly Linked List
12. Display Size

### Java Code

```java
package linkedList;

class Node {
    int val;
    Node prev;
    Node next;
}

class Double_LinkedList {

    Node head, tail;
    int size = 0;

    // Creation of DLL
    public void creation(int data) {

        Node node = new Node();

        node.val = data;
        node.prev = null;
        node.next = null;

        head = tail = node;
        size = 1;
    }

    // Insertion
    public void insertion(int loc, int value) {

        if (loc < 0) {
            System.out.println("Invalid location");
            return;
        }

        if (head == null) {
            if (loc == 0) {
                creation(value);
            } else {
                System.out.println("Invalid location");
            }
            return;
        }

        Node node = new Node();
        node.val = value;

        // Insert at beginning
        if (loc == 0) {

            node.prev = null;
            node.next = head;

            head.prev = node;
            head = node;
        }

        // Insert at end
        else if (loc >= size) {

            node.next = null;
            node.prev = tail;

            tail.next = node;
            tail = node;
        }

        // Insert at specific position
        else {

            Node temp = head;

            for (int i = 0; i < loc - 1; i++) {
                temp = temp.next;
            }

            node.next = temp.next;
            node.prev = temp;

            temp.next.prev = node;
            temp.next = node;
        }

        size++;
    }

    // Forward Traversal
    public void fwdTraversal() {

        Node temp = head;

        while (temp != null) {
            System.out.print(temp.val + " <-> ");
            temp = temp.next;
        }

        System.out.println("null");
    }

    // Backward Traversal
    public void bwdTraversal() {

        Node temp = tail;

        while (temp != null) {
            System.out.print(temp.val + " <-> ");
            temp = temp.prev;
        }

        System.out.println("null");
    }

    // Search
    public void search(int data) {

        Node temp = head;

        while (temp != null) {

            if (temp.val == data) {
                System.out.println("The data is present");
                return;
            }

            temp = temp.next;
        }

        System.out.println("Data Not found");
    }

    // Find Middle
    public void find_Mid() {

        if (head == null) {
            System.out.println("DLL is empty");
            return;
        }

        Node fast = head;
        Node slow = head;

        while (fast != null && fast.next != null) {

            slow = slow.next;
            fast = fast.next.next;
        }

        System.out.println("Mid value is: " + slow.val);
    }

    // Reverse DLL
    public void reverse() {

        Node curr = head;

        while (curr != null) {

            Node temp = curr.prev;

            curr.prev = curr.next;
            curr.next = temp;

            curr = curr.prev;
        }

        Node temp = head;
        head = tail;
        tail = temp;

        System.out.println("DLL Reversed");
    }

    // Delete First Node
    public void deleteFirst() {

        if (head == null) {
            System.out.println("DLL is empty");
            return;
        }

        if (head == tail) {
            head = tail = null;
        } else {

            head = head.next;
            head.prev = null;
        }

        size--;

        System.out.println("First node deleted");
    }

    // Delete Last Node
    public void deleteLast() {

        if (tail == null) {
            System.out.println("DLL is empty");
            return;
        }

        if (head == tail) {
            head = tail = null;
        } else {

            tail = tail.prev;
            tail.next = null;
        }

        size--;

        System.out.println("Last node deleted");
    }

    // Delete at Specific Position
    public void deleteAtPosition(int loc) {

        if (loc < 0 || loc >= size) {
            System.out.println("Invalid location");
            return;
        }

        if (loc == 0) {
            deleteFirst();
            return;
        }

        if (loc == size - 1) {
            deleteLast();
            return;
        }

        Node temp = head;

        for (int i = 0; i < loc; i++) {
            temp = temp.next;
        }

        temp.prev.next = temp.next;
        temp.next.prev = temp.prev;

        size--;

        System.out.println("Node deleted at position " + loc);
    }

    // Delete Entire DLL
    public void delete() {

        head = tail = null;
        size = 0;

        System.out.println("DLL is deleted");
    }

    // Display Size
    public void displaySize() {

        System.out.println("Size: " + size);
    }
}

public class MainClass {

    public static void main(String[] args) {

        Double_LinkedList dll = new Double_LinkedList();

        // Creation
        dll.creation(10);

        // Insertion
        dll.insertion(1, 20);
        dll.insertion(2, 30);
        dll.insertion(3, 40);
        dll.insertion(2, 50);

        // Forward Traversal
        System.out.println("Forward Traversal:");
        dll.fwdTraversal();

        // Backward Traversal
        System.out.println("\nBackward Traversal:");
        dll.bwdTraversal();

        // Search
        System.out.println("\nSearch:");
        dll.search(30);

        // Find Middle
        System.out.println("\nFind Middle:");
        dll.find_Mid();

        // Display Size
        dll.displaySize();

        // Reverse
        System.out.println("\nReverse:");
        dll.reverse();
        dll.fwdTraversal();

        // Delete First
        System.out.println("\nDelete First:");
        dll.deleteFirst();
        dll.fwdTraversal();

        // Delete Last
        System.out.println("\nDelete Last:");
        dll.deleteLast();
        dll.fwdTraversal();

        // Delete at Position
        System.out.println("\nDelete at Position:");
        dll.deleteAtPosition(1);
        dll.fwdTraversal();

        // Display Size
        dll.displaySize();

        // Delete Entire DLL
        System.out.println("\nDelete Entire DLL:");
        dll.delete();
        dll.fwdTraversal();
    }
}
```

### Sample Output

```text
Forward Traversal:
10 <-> 20 <-> 50 <-> 30 <-> 40 <-> null

Backward Traversal:
40 <-> 30 <-> 50 <-> 20 <-> 10 <-> null

Search:
The data is present

Find Middle:
Mid value is: 50
Size: 5

Reverse:
DLL Reversed
40 <-> 30 <-> 50 <-> 20 <-> 10 <-> null

Delete First:
First node deleted
30 <-> 50 <-> 20 <-> 10 <-> null

Delete Last:
Last node deleted
30 <-> 50 <-> 20 <-> null

Delete at Position:
Node deleted at position 1
30 <-> 20 <-> null
Size: 2

Delete Entire DLL:
DLL is deleted
null
```

````
````markdown
# Reverse a String Using Linked List

## Question 3

**Problem:**  
Write a Java program to reverse a given string using a Singly Linked List.

### Java Code

```java
package linkedList;

class Node {
    char data;
    Node next;
}

class StringLinkedList {

    Node head;

    // Insert character at beginning
    public void insert(char value) {

        Node node = new Node();
        node.data = value;
        node.next = head;

        head = node;
    }

    // Display Linked List
    public void display() {

        Node temp = head;

        while (temp != null) {
            System.out.print(temp.data);
            temp = temp.next;
        }

        System.out.println();
    }

    // Reverse String using Linked List
    public void reverseString(String str) {

        for (int i = 0; i < str.length(); i++) {
            insert(str.charAt(i));
        }
    }
}

public class MainClass {

    public static void main(String[] args) {

        String str = "HELLO";

        StringLinkedList list = new StringLinkedList();

        System.out.println("Original String: " + str);

        list.reverseString(str);

        System.out.print("Reversed String: ");
        list.display();
    }
}
```

### Sample Output

```text
Original String: HELLO
Reversed String: OLLEH
```



````
````markdown
