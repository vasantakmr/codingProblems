---
title: 'Introduction to Trees'
tocTitle: 'Introduction'
description: ''
commit: 'ac1ec13'
---


```cpp
// Node Structure
struct Node 
{ 
    int data; 
    struct Node* left, *right; 
    Node(int data) 
    { 
        this->data = data; 
        left = right = NULL; 
    } 
};
```

```cpp
// Size of Binary Tree (Number of elements in tree)
int getSize(Node* node)
{
    if(node) {
        int l = getSize(node->left);
        int r = getSize(node->right);
        return l+r+1;
    } else {
        return 0;
    }
}
```

```cpp 
// Height if a Binary tree
int height(struct Node* node){
    if(node) {
        int l = height(node->left);
        int r = height(node->right);
        return 1+max(l,r);
    } else {
        return 0;
    }
}
```

Tree Traversals:

```cpp
// In Order traversal
void printInOrder(Node* root) {
    if(root==NULL) 
        return;
    printInOrder(root->left);
    cout<<root->data<<endl;
    printInOrder(root->right);
}
```

```cpp
// Pre Order traversal
void preOrder(Node *root) {
    cout<<root->data<<" ";
    if(root->left) {
        preOrder(root->left);
    }
    if(root->right) {
        preOrder(root->right);
    }
}

```

```cpp
// Post Order traversal
void printPostOrder(Node* root) {
    if(root==NULL) 
        return;
    printPostOrder(root->left);
    printPostOrder(root->right);
    cout<<root->data<<endl;
}
```

```cpp
// Check if 2 trees are identical
bool isIdentical(Node *r1, Node *r2)
{
    if(r1==NULL && r2==NULL)
        return true;

    if(r1!=NULL && r2!=NULL)
        return (r1->data == r2->data) 
        && isIdentical(r1->left, r2->left) 
        && isIdentical(r1->right, r2->right);

    return 0;
}
```

```cpp
// mirroring a tree
void mirrorATree(Node* root) {
    if(root==NULL) {
        return;
    } else {
        struct Node* temp;
        mirrorATree(root->left);
        mirrorATree(root->right);
        temp = root->left;
        root->left = root->right;
        root->right = temp;
    }
}
```

```cpp
// count the number of Leaf Nodes
int countLeafNodes(Node* root)
{
    if(root == NULL) {
        return 0;
    } else if(root->left ==NULL 
        && root->right == NULL) {
        return 1;
    } else {
        return countLeafNodes(root->left) + 
        countLeafNodes(root->right);
    }
}
```

```cpp
// Minimum Value in BST
int minValue(Node* root)
{
    if(root->left == NULL)
        return root->data;
    else
        minValue(root->left);
}
```