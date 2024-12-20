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