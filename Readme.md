# binary tree

# type of binary tree
1. full binary tree

a tree either have 0 children or 2 children that type of tree called as full binary tree.

2. complete binary tree

A Complete Binary Tree is a type of binary tree in which all the levels, except possibly the last one, are completely filled, and all the nodes in the last level are as far left as possible. This ensures the tree is balanced to a certain degree.

3. perfect binary tree

A Perfect Binary Tree is a type of binary tree in which all internal nodes have exactly two children, and all leaf nodes are at the same level. In other words, a perfect binary tree is completely filled at every level.

4. balanced binary tree

balanced binary tree is that tye of binary tree which length can be maximum log(n) where n is the number of the nodes

5. degenerate tree:
A Degenerate Tree (or Pathological Tree) is a type of binary tree where every parent node has only one child. This makes the tree essentially resemble a linked list, as there is no branching or balancing.


# Python Code for Binary Tree Representation

class Node:
    def __init__(self, value):
        self.value = value   # Store the node's value
        self.left = None     # Pointer to the left child
        self.right = None    # Pointer to the right child

# Example of creating a simple binary tree
if __name__ == "__main__":
    # Create root node
    root = Node(1)
    
    # Add children to root
    root.left = Node(2)
    root.right = Node(3)
    
    # Add children to left child of root
    root.left.left = Node(4)
    root.left.right = Node(5)
    
    # Add children to right child of root
    root.right.left = Node(6)
    root.right.right = Node(7)


    # bfs and dfs in binary tree
# there is three type of dfs in binary tree
1. inorder traversal
2. preorder traversal 
3. post order traversal

pre order traversal in binary tree

Recursive Preorder Traversal
python
Copy code
class Node:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

def preorder_recursive(node):
    if node is not None:
        print(node.value, end=" ")  # Visit the root
        preorder_recursive(node.left)  # Traverse left subtree
        preorder_recursive(node.right)  # Traverse right subtree

# Example Usage
if __name__ == "__main__":
    # Create the binary tree
    root = Node(1)
    root.left = Node(2)
    root.right = Node(3)
    root.left.left = Node(4)
    root.left.right = Node(5)
    root.right.left = Node(6)
    root.right.right = Node(7)

    print("Preorder Traversal (Recursive):")
    preorder_recursive(root)  

iterative preorder traversal

def preorder_iterative(root):
    if root is None:
        return 
    stack=[root]
    while stack:
        current=stack.pop();
        print(current.value,end="")
        if current.right:
            stack.append(current.right)
        if current.left:
            stack.append(current.left)
if __name__=="__main__":
    print("\n PREORDER TRAVERSAL (ITERATIVE)")
    PREORDER_ITERATIVE(ROOT)

# recursive inorder traversal

Recursive Inorder Traversal
python
Copy code
class Node:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

def inorder_recursive(node):
    if node is not None:
        inorder_recursive(node.left)  # Traverse left subtree
        print(node.value, end=" ")   # Visit the root
        inorder_recursive(node.right)  # Traverse right subtree

# Example Usage
if __name__ == "__main__":
    # Create the binary tree
    root = Node(1)
    root.left = Node(2)
    root.right = Node(3)
    root.left.left = Node(4)
    root.left.right = Node(5)
    root.right.left = Node(6)
    root.right.right = Node(7)

    print("Inorder Traversal (Recursive):")
    inorder_recursive(root) 

# iterative inorder traversal
def inorder_traversal(root):
    stack=[]
    current=root
    while stack or current:
        while current:
            stack.append(current)
            current=current.left
        current=stack.pop()
        print(current.value,end="")
        current=current.right
if __name__="__main__":
    print("\n order traversal (iterative)")
    inorder_traversalo(root)

class BInarytree:
    def __init__(self):
        self.root=None
    def insert(self,value):
        if self.root is None:
            self.root=Node(value)
        else:
            self._insert(value,self.root)
    def _insert(self, value,current_node):
        if value<current_node.value:
            if current_node.left is None:
                current_node.left=Node(value)
            else:
                self._insert(value,current_node.left)
        elif value>current_node.value:
            if current_node.right is None:
                current_node.right=Node(value)
            else:
                self._insert(value,current_node.right)
        else:
            print(f"Value {value} already exist in the tree")
    def inorder_traversal(self,node):
        if node is not None:
            self.inorder_traversal(node.left)
            print(node.value,end="")
            self.inorder_traversal(node.right)
#using the binary tree 
bt=BinaryTree()
values=[10,5,15,3,7,12,18]
for val in values:
    bt.insert(val)
print("inorder_traversal")
bt.inorder_traversal(bt.root)

# binary tree representation in java

1. node representation:
eaqch node of the binary tree 
contains:
a value 
a pointer to the left child 
a pointer to the right child

class Node{
    int value;
    Node left;
    Node right;
    Node (int value){
        this.value=value;
        left=null;
        right=null;
    }
}

2 . binary tree class
a class to represent the binary tree , it includes methods like traveersal , insertion , deletion 
class BinaryTree{
    Node root;
    BinaryTree(){
        root=null;
    }
    void insert(int value){
        root=insertRec(root,value);
    }
    Node insertRec(Node root, int value){
        if (root==null){
            root=new Node(value);
            return root;
        }
        if (value<root.value){
            root.left=insertRec(root.left,value);
        }
        else if(value>root.value){
            root.right=insertrec(root.right,value);
        }
        return root;
    }
    void inorderTraversal(){
        inorderRec(root);
    }
    void inorderRec(Node root){
        if (root!=null){
            inorderRec(root.left);
            System.out.println(root.value+" ");
            inorderrec(root.right);
        }

    }
}

# 3. using the binary tree:
public class Main{
    public static void main(String[] args){
        BinaryTree bt=new BinaryTree();
        int[] values={10,5,15,3,7,12,18};
        for(int value:values){
            bt.insert(value);
        }
        System.out.println("Inorder traversal");
        bt.inorderTraversal();
    }
}

# binary tree traversal in bfs
from collection import deque
class Treenode:
    def __init__(self, value=0,left=None,right=None):
        self.value=value
        self.left=left
        self.right=right
    def bfs(root):
        if not root:
            return 
        queue=deque([root])
        while queue:
            node=queue.popleft()
            print(node.value,end="")
            if node.left:
                queue.append(node.left)
            if node.right:
                queue.append(node.right)
root=TreeNode(1,TreeNode(2),TreeNode(3))
bfs(root)

# dfs 
1. inorder traversal (left, root, right)
2. pre-order traversal(root,left,right)
3. post-order traversal(left,right ,root)

1. inorder traversal :
def inorder(root):
    if root:
        inorder(root.left)
        print(root.value,end="")
        inorder(root.right)
inorder(root)

2. pre order traversal :
def preorder(root):
    if root:
        print(root.vaue,end=" ")
        preorder(root.left)
        preorder(root.right)
preorder(root)

3. post order traversal:

def postorder(root):
    if root:
        postorder(root.left)
        postorder(root.right)
        print(root.value,end=" ")
postorder(root)