````markdown

# Quick Sort

## Question 1

**Problem:**  
Write a Java program to sort an array in ascending order using the Quick Sort algorithm.

### Java Code

```java
package ds_pro;

import java.util.Arrays;

public class quickSort {

    public static int partition(int[] arr, int low, int high) {

        int pivot = high;
        int j = low - 1;

        for (int i = low; i <= high; i++) {

            if (arr[i] <= arr[pivot]) {

                j++;

                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }

        return j;
    }

    public static void quicksort(int[] arr, int low, int high) {

        if (low < high) {

            int pivot = partition(arr, low, high);

            quicksort(arr, low, pivot - 1);
            quicksort(arr, pivot + 1, high);
        }
    }

    public static void main(String[] args) {

        int[] arr = {5, 8, 7, 6, 9, 1, 2, 3, 4};

        System.out.println("Before Sorting: " + Arrays.toString(arr));

        quicksort(arr, 0, arr.length - 1);

        System.out.println("After Sorting: " + Arrays.toString(arr));
    }
}
```

### Sample Output

```text
Before Sorting: [5, 8, 7, 6, 9, 1, 2, 3, 4]
After Sorting: [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

````
````markdown
# Merge Sort

## Question 2

**Problem:**  
Write a Java program to sort an array in ascending order using the Merge Sort algorithm.

### Java Code

```java
package ds_pro;

import java.util.Arrays;

public class mergeSort {

    public static void divide(int[] arr, int low, int high) {

        if (low < high) {

            int mid = (low + high) / 2;

            divide(arr, low, mid);       // Left half
            divide(arr, mid + 1, high);  // Right half

            merge(arr, low, mid, high);
        }
    }

    public static void merge(int[] arr, int low, int mid, int high) {

        int[] temp = new int[high - low + 1];

        int left = low;
        int right = mid + 1;
        int index = 0;

        while (left <= mid && right <= high) {

            if (arr[left] <= arr[right]) {
                temp[index] = arr[left];
                left++;
            } else {
                temp[index] = arr[right];
                right++;
            }

            index++;
        }

        while (left <= mid) {
            temp[index++] = arr[left++];
        }

        while (right <= high) {
            temp[index++] = arr[right++];
        }

        for (int i = 0; i < temp.length; i++) {
            arr[low + i] = temp[i];
        }
    }

    public static void main(String[] args) {

        int[] arr = {5, 8, 7, 6, 9, 1, 2, 3, 4};

        System.out.println("Before Sorting: " + Arrays.toString(arr));

        divide(arr, 0, arr.length - 1);

        System.out.println("After Sorting: " + Arrays.toString(arr));
    }
}
```

### Sample Output

```text
Before Sorting: [5, 8, 7, 6, 9, 1, 2, 3, 4]
After Sorting: [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

````
````markdown
# Linked List – Singly Linked List

## Question 3

**Problem:**  
Write a Java program to implement a singly linked list with the following operations:

- Insert at First
- Insert at Middle
- Insert at Last
- Delete First
- Delete Middle
- Delete Last
- Find an Element
- Display Linked List

### Java Code

```java
package linkedlist;

class LL {

    private class Node {
        private int value;
        private Node next;

        public Node(int value) {
            this.value = value;
        }

        public Node(int value, Node next) {
            this.value = value;
            this.next = next;
        }
    }

    private Node head;
    private Node tail;
    private int size;

    public LL() {
        this.size = 0;
    }

    // Insert at First
    public void insertfirst(int val) {

        Node node = new Node(val);
        node.next = head;
        head = node;

        if (tail == null) {
            tail = head;
        }

        size++;
    }

    // Insert at Middle
    public void insertmid(int val, int index) {

        if (index == 0) {
            insertfirst(val);
            return;
        }

        if (index == size) {
            insertlast(val);
            return;
        }

        Node temp = head;

        for (int i = 0; i < index - 1; i++) {
            temp = temp.next;
        }

        Node node = new Node(val, temp.next);
        temp.next = node;

        size++;
    }

    // Insert at Last
    public void insertlast(int val) {

        if (tail == null) {
            insertfirst(val);
            return;
        }

        Node node = new Node(val);
        tail.next = node;
        tail = node;

        size++;
    }

    // Delete First
    public int deletefirst() {

        int val = head.value;
        head = head.next;

        if (head == null) {
            tail = null;
        }

        size--;

        return val;
    }

    // Delete Middle
    public int deletemid(int index) {

        if (index == 0) {
            return deletefirst();
        }

        if (index == size - 1) {
            return deletelast();
        }

        Node prev = get(index - 1);
        int val = prev.next.value;

        prev.next = prev.next.next;
        size--;

        return val;
    }

    // Delete Last
    public int deletelast() {

        if (size <= 1) {
            return deletefirst();
        }

        Node secondlast = get(size - 2);
        int val = tail.value;

        tail = secondlast;
        tail.next = null;

        size--;

        return val;
    }

    // Get Node by Index
    public Node get(int index) {

        Node node = head;

        for (int i = 0; i < index; i++) {
            node = node.next;
        }

        return node;
    }

    // Find Element
    public Node find(int val) {

        Node node = head;

        while (node != null) {

            if (node.value == val) {
                return node;
            }

            node = node.next;
        }

        return null;
    }

    // Display Linked List
    public void display() {

        Node temp = head;

        while (temp != null) {
            System.out.print(temp.value + "-->");
            temp = temp.next;
        }

        System.out.print("END");
    }
}

class Linky {

    public static void main(String[] args) {

        LL l = new LL();

        l.insertfirst(10);
        l.insertfirst(20);
        l.insertfirst(30);
        l.insertlast(40);
        l.insertmid(50, 2);

        l.display();

        System.out.println();

        System.out.println(l.deletefirst());

        l.display();
    }
}
```

### Sample Output

```text
30-->20-->50-->10-->40-->END
30
20-->50-->10-->40-->END
```

````
````markdown

````
````markdown

````
````markdown

````
````markdown

````
````markdown

