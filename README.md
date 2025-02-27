
Download Link : https://programming.engineering/product/project-4-its-just-a-jump-to-the-left-and-a-step-to-the-right/

# CSCI-241

 🔍 Project 4: It's Just a Jump to the Left and a Step to the Right Project 4: It’s Just a Jump to the Left and a Step to the Right
In this project, you will implement a basic unbalanced binary search tree and then add balance features to obtain optimal height.

Part I – Unbalanced Tree

Your primary focus in this part is recursion. Conceptually, binary search trees are fairly simple structures, so let’s take advantage of this implementation to develop our recursion skills. Review the recursive algorithm description in the BST slide deck very carefully. The wording is deliberate, and your implementation must follow the presented algorithms. We also suggest reviewing the associated videos to ensure that you understand the concepts before beginning your implementation.

When considering the traversal methods (which must also be recursive), remember that recursion works by dividing the problem into smaller components, then combining the smaller results to form the larger solution during the return path. Strings can be concatenated together to form larger strings using the + operator. Review the traversal algorithms and consider how the process of building the string can be divided into smaller steps and how those smaller strings can be combined to form the larger result. As one example, notice that the in-order traversal of a subtree rooted at node t is the concatenation of three strings: the in-order traversal of the subtree rooted at t’s left child, t’s value, and the in-order traversal of the subtree rooted at t’s right child.

Your implementation will also provide a get_height() method to obtain the number of levels in the tree. Note that this method is specified to operate in constant time. This means that height cannot be computed on demand, as counting the levels yields linear-time performance. Instead, add an attribute to the __Node class to store the height of the subtree rooted at that node. Just before returning a node reference at the end of a recursive call, update that node’s height field to be correct. If you do this before each return, then you know at all times that the height field of every node below you in the tree has the correct value. Because the heights of the subtrees rooted at t‘s children are now known to be correct, we can say that t‘s height is equal to the maximum of its children’s heights (accessible in constant time through child node attributes) plus 1. An important consideration here is that a non-existent subtree has height 0 (be careful not to crash in this case). Also notice that the height of the subtree rooted at a newly created node object is always 1.

In the example below, t‘s height should be updated to ℎ + 1 before it is returned. We choose ℎ because the right subtree’s height is larger than the left subtree’s height. If every node in the tree stores the height of the subtree rooted at that node, then you can return the height of the entire tree in constant time.

subtree it is balanced and the height attribute of every node at or below t is correct (but only reevaluate the heights of nodes whose subtrees could potentially have changed—that is, every node on the insertion/removal path and every node actively involved in a rotation).

Once you have balanced insertions and removals implemented, implement the public/private method pair for recursively constructing a Python list of the values in the tree. This method should work just like the in-order traversal methods, but it should return a python list, not a string.

Finally, complete the implementation of the provided Fraction class by implementing the three comparison operators. The main section of this program should create a Python list of fraction objects, then insert them one at a time into an initially empty AVL tree, then get the in-order Python list representation using the new to_list method of Binary_Search_Tree, showing that the returned list is in sorted order.

SUBMISSION EXPECTATIONS

Binary_Search_Tree.py This should be your implementation of an AVL tree. You are free to add additional private support methods (in fact, this is necessary), but do not change the public interface to this class.

BST_Test.py Your unit tests for implementations. No skeleton file is provided for this component. For testing, notice that the three traversals (in-order, post-order, and pre-order) uniquely identify a binary search tree. No two unequal trees share all three traversal orderings. Ensure that your traversals work correctly and use the combination of all three of them to test the structure of the tree after insertion and removal operations.

Fraction.py The provided Fraction class with the comparison methods implemented and with the main section sorting a Python list of fraction objects.
