````
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

````
````markdown
