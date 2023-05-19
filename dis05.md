# Tree

trees are recursive data structures that are widely used in various settings and can be implemented in many ways.

Notice that the tree branches downward. In computer science, the root of a tree starts at the top, and the leaves are at the bottom.

Some terminology regarding trees:

* Parent Node: A node that has at least one branch.
* Child Node: A node that has a parent. A child node can only have one parent.
* Root: The top node of the tree. In our example, this is the 1 node.
* Label: The value at a node. In our example, every node's label is an integer.
* Leaf: A node that has no branches. In our example, the 4, 5, 6, 2 nodes are leaves.
* Branch: A subtree of the root. Trees have branches, which are trees themselves: this is why trees are recursive data structures.
* Depth: How far away a node is from the root. We define this as the number of edges between the root to the node. As there are no edges between the root and itself, the root has depth 0. In our example, the 3 node has depth 1 and the 4 node has depth 2.
* Height: The depth of the lowest (furthest from the root) leaf. In our example, the 4, 5, and 6 nodes are all the lowest leaves with depth 2. Thus, the entire tree has height 2.
In computer science, there are many different types of trees.Some vary in the number of branches each node has; others vary in the structure of the tree.

```python
def flatten(s):
    """Returns a flattened version of list s.
    lst = []
    for elem in s:
        if type(elem) == list:
            lst += flatten(elem)
        else:
            lst += [elem]
    return lst
```

```python
def tree(label, branches=[]):
    """Construct a tree with the given label value and a list of branches."""
    return [label] + list(branches)

def label(tree):
    """Return the label value of a tree."""
    return tree[0]

def branches(tree):
    """Return the list of branches of the given tree."""
    return tree[1:]

def is_leaf(tree):
    """Returns True if the given tree's list of branches is empty, and False
    otherwise.
    """
    return not branches(tree)
```
