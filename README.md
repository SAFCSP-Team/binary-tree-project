# Binary tree project
   
### Objective
This project aims to understand how to build the binary tree.
  
### Problem  
Create a binary tree for computer storage as below (Figure 1):
  
  
Figure 1    
<img width="910" alt="Introduction to Arrays-01" src="https://github.com/SAFCSP-Team/data-structures-and-algorithms-bootcamp/blob/main/data-structures-and-algorithms-101/02-data-structures/05-tree/images/Binary-tree-project.jpg">
  
  
### Implementation  
Using Java programming language: 
  
- The `Node` class is already implemented and added to the source file - java as the below:   
```java
class Node {

    String fileName;

    Node right;
    Node left;

    public Node(String fileName) {
        this.fileName = fileName;
        this.right = null;
        this.left = null;
    }
}

```


- The `BinaryTree` class is already implemented and added to the source file - java as the below:

```java
import java.util.Stack;

class BinaryTree {

  Node root;

  public BinaryTree(Node root) {
    this.root = root;
  }


  // Pre-order traverse
  public void print() {

    if (this.root == null) {
      System.out.println("Tree is empty");
      return;
    }

    Stack<Node> stack = new Stack<>();
    stack.push(root);

    while (!stack.isEmpty()) {
      Node currentNode = stack.pop();

      System.out.println(" " + currentNode.fileName);

      if (currentNode.right != null) {
        stack.push(currentNode.right);
      }

      if (currentNode.left != null) {
        stack.push(currentNode.left);
      }

    }
    return;
  }

  public Node search(String target) {

    if (this.root == null) {
      System.out.println("Tree is empty");
      return null;
    }

    Stack<Node> stack = new Stack<>();
    stack.push(this.root);

    while (!stack.isEmpty()) {
      Node currentNode = stack.pop();

      if (currentNode.fileName == target) {
        return currentNode;
      }

      if (currentNode.right != null) {
        stack.push(currentNode.right);
      }

      if (currentNode.left != null) {
        stack.push(currentNode.left);
      }

    }
    return null;
  }

  public void addRight(String parentData, String newData) {

    Node newNode = new Node(newData);
    Node parent = search(parentData);

    if (parent != null) {

      if (parent.right == null) {
        parent.right = newNode;
        System.out.println(newNode.fileName + " added successfully");
      } else {
        System.out.println("parent already has a right child");
        return;
      }
    } else {
      System.out.println(parent + " parent not fount");
    }

  }

  public void addLeft(String parentData, String newData) {

    Node newNode = new Node(newData);
    Node parent = search(parentData);

    if (parent != null) {

      if (parent.left == null) {
        parent.left = newNode;
        System.out.println(newNode.fileName + " added successfully");
      } else {
        System.out.println("parent already has a left child");
        return;
      }
    } else {
      System.out.println(parentData + " parent not fount");
    }

  }

}

```  
  
In the `main` method perform the following actions:

1 - Create a BinaryTree object holding the root node.   
2 - Add the rest of the node to complete the tree.     
3 - Run the code.

```java

  public static void main(String[] args) {

  /* add your code here */

  }


```
