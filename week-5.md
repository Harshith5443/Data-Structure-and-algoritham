
````markdown
# Binary Search Tree (BST)

## Question 1

**Problem:**  
Write a Java program to implement a Binary Search Tree (BST) with the following operations:

1. Create a node path.
2. Insert data into the BST.
3. Preorder Traversal (Root, Left, Right).
4. Inorder Traversal (Left, Root, Right).
5. Postorder Traversal (Left, Right, Root).

### Java Code

```java
class Node {
    int value;
    Node left, right;
}

class BinarySearchTree {

    Node rootNode;

    // Create Node Path
    public Node createNodePath(Node cn, int data) {

        if (cn == null) {

            Node node = new Node();
            node.value = data;

            System.out.println("Node value is: " + data);

            return node;
        }
        else if (data < cn.value) {

            cn.left = createNodePath(cn.left, data);
            return cn;
        }
        else {

            cn.right = createNodePath(cn.right, data);
            return cn;
        }
    }

    // Insert Data
    public void insertData(int data) {

        rootNode = createNodePath(rootNode, data);
    }

    // Preorder: Root, Left, Right
    public void preOrder(Node root) {

        if (root == null) {
            return;
        }

        System.out.print(root.value + " ");

        preOrder(root.left);
        preOrder(root.right);
    }

    // Inorder: Left, Root, Right
    public void inOrder(Node root) {

        if (root == null) {
            return;
        }

        inOrder(root.left);

        System.out.print(root.value + " ");

        inOrder(root.right);
    }

    // Postorder: Left, Right, Root
    public void postOrder(Node root) {

        if (root == null) {
            return;
        }

        postOrder(root.left);
        postOrder(root.right);

        System.out.print(root.value + " ");
    }
}

public class MainClass {

    public static void main(String[] args) {

        BinarySearchTree bst = new BinarySearchTree();

        // Insert Data
        bst.insertData(7);
        bst.insertData(6);
        bst.insertData(8);
        bst.insertData(3);
        bst.insertData(1);
        bst.insertData(9);
        bst.insertData(4);
        bst.insertData(5);
        bst.insertData(0);
        bst.insertData(2);

        // Preorder
        System.out.println("\n--------- Pre Order ---------");
        bst.preOrder(bst.rootNode);

        // Inorder
        System.out.println("\n\n--------- In Order ---------");
        bst.inOrder(bst.rootNode);

        // Postorder
        System.out.println("\n\n--------- Post Order ---------");
        bst.postOrder(bst.rootNode);

        System.out.println();
    }
}
```

### Sample Output

```text
Node value is: 7
Node value is: 6
Node value is: 8
Node value is: 3
Node value is: 1
Node value is: 9
Node value is: 4
Node value is: 5
Node value is: 0
Node value is: 2

--------- Pre Order ---------
7 6 3 1 0 2 4 5 8 9

--------- In Order ---------
0 1 2 3 4 5 6 7 8 9

--------- Post Order ---------
0 2 1 5 4 3 6 9 8 7
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
