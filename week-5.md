
````markdown
# Binary Search Tree (BST)

## Question 1

**Problem:**  
Write a Java program to implement a Binary Search Tree with the following operations:

1. Create a Node and Insert Data
2. Insert Data into the BST
3. Preorder Traversal (Root → Left → Right)
4. Inorder Traversal (Left → Root → Right)
5. Postorder Traversal (Left → Right → Root)

### Java Code

**Node.java**

```java
package binarysearchtree;

public class Node {

    int value;
    Node left;
    Node right;
}
```

**BinarySearchTree.java**

```java
package binarysearchtree;

public class BinarySearchTree {

    Node rootNode;

    // Create Node and Insert Data
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

    // Preorder Traversal
    // Root -> Left -> Right
    public void preOrder(Node root) {

        if (root == null) {
            return;
        }

        System.out.print(root.value + " ");

        preOrder(root.left);
        preOrder(root.right);
    }

    // Inorder Traversal
    // Left -> Root -> Right
    public void inOrder(Node root) {

        if (root == null) {
            return;
        }

        inOrder(root.left);

        System.out.print(root.value + " ");

        inOrder(root.right);
    }

    // Postorder Traversal
    // Left -> Right -> Root
    public void postOrder(Node root) {

        if (root == null) {
            return;
        }

        postOrder(root.left);
        postOrder(root.right);

        System.out.print(root.value + " ");
    }
}
```

**MainClass.java**

```java
package binarysearchtree;

public class MainClass {

    public static void main(String[] args) {

        BinarySearchTree bst = new BinarySearchTree();

        // Insert Data
        bst.insertData(50);
        bst.insertData(30);
        bst.insertData(70);
        bst.insertData(20);
        bst.insertData(40);
        bst.insertData(60);
        bst.insertData(80);

        // Preorder Traversal
        System.out.println("\nPreorder Traversal:");
        bst.preOrder(bst.rootNode);

        // Inorder Traversal
        System.out.println("\n\nInorder Traversal:");
        bst.inOrder(bst.rootNode);

        // Postorder Traversal
        System.out.println("\n\nPostorder Traversal:");
        bst.postOrder(bst.rootNode);
    }
}
```

### Sample Output

```text
Node value is: 50
Node value is: 30
Node value is: 70
Node value is: 20
Node value is: 40
Node value is: 60
Node value is: 80

Preorder Traversal:
50 30 20 40 70 60 80

Inorder Traversal:
20 30 40 50 60 70 80

Postorder Traversal:
20 40 30 60 80 70 50
```

### Binary Search Tree Structure

```text
          50
        /    \
       30     70
      / \    / \
     20  40  60  80
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
