#### Explain what a 'TreeWalker' is. Describe how to create one and give at least two examples of its usage.

# Using TreeWalkers

A `TreeWalker` is an object containing the subtree nodes of a specific node. It is an useful tool to traverse a node subtree, as it contains a pointer to the node which is currently pointing at. It also provides several methods to manipulate that pointer.

## Creating a TreeWalker

To create a TreeWalker we will use the `document.createTreeWalker()` method, which will return a brand new TreeWalker object. This method accepts three parameters:

- `root`: the root Node of the tree. The TreeWalker will contain all the subtree nodes of this root Node.
- `whatToShow`: it is an optional constant used to specify what types of Node will be include in the subtree. Note that the children of an skipped node may be included. The non-deprecated values for this parameter are:

  - NodeFilter.SHOW_ALL: Shows all nodes.
  - NodeFilter.SHOW_COMMENT: Shows Comment nodes.
  - NodeFilter.SHOW_DOCUMENT: Shows Document nodes.
  - NodeFilter.SHOW_DOCUMENT_FRAGMENT: Shows DocumentFragment nodes.
  - NodeFilter.SHOW_DOCUMENT_TYPE: Shows DocumentType nodes.
  - NodeFilter.SHOW_ELEMENT: Shows Element nodes.
  - NodeFilter.SHOW_PROCESSING_INSTRUCTION: Shows ProcessingInstruction nodes.
  - NodeFilter.SHOW_TEXT: Shows Text nodes.

- `filter`: an optional object with an `acceptNode` method. This method will evaluate every single node and return one of the following values which will tell what to do with the evaluated node:

  - `FILTER_ACCEPT`: the node should be accepted.
  - `FILTER_REJECT`: the node should be rejected. Child nodes are also rejected.
  - `FILTER_SKIP`: the node should be skipped but not its children, which will be evaluated later.

Say we have the following HTML sample:

```html
<div id="tree-root">
  Inner Text
  <h1>Title</h1>
  <ul>
    <li>Item 1</li>
    <li class="select">Item 2</li>
    <li>Item 3</li>
    <li>Item 4</li>
    <li>Item 5</li>
  </ul>
  <!--Comment Node -->
</div>

```

Let's create some TreeWalkers:

```js
const root = document.getElementById('tree-root');
const tw = document.createTreeWalker(root, NodeFilter.SHOW_ALL);
// tw will contain all the nodes including text nodes and comments
// [text, h1, text, text, ul, text, li, text, text, li.select, text, text, li, text, text, li, text, text, li, text, text, text, comment, text]

const tw2 = document.createTreeWalker(root, NodeFilter.SHOW_ELEMENT);
// tw2 will contain only the Element nodes
// [h1, ul, li, li.select, li, li, li]

const tw3 = document.createTreeWalker(root, NodeFilter.SHOW_ELEMENT, {
  acceptNode: function(node) {
    if (node.classList.contains('select')) {
      return NodeFilter.FILTER_ACCEPT;
    } else {
      return NodeFilter.FILTER_SKIP;
    }
  }
});
// tw3 will contain only the LI element with the select class
// [li.select]

```

## Traversing a TreeWalker

TreeWalkers provide properties and methods to traverse the subtree nodes. Note that these methods only consider visible DOM nodes:

- `TreeWalker.currentNode`: the currently pointed Node
- `TreeWalker.parentNode()`: moves the pointer to the first visible ancestor of the current element and returns that ancestor
- `TreeWalker.firstChild()`: moves the pointer to the first visible child of the current element and returns that child
- `TreeWalker.lastChild()`: moves the pointer to the last visible child of the current element and returns that child
- `TreeWalker.previousSibling()`: moves the pointer to the previous sibling of the current element and returns that sibling
- `TreeWalker.nextSibling()`: moves the pointer to the next sibling of the current element and returns that sibling
- `TreeWalker.previousNode()`: moves the pointer to the previous node in the subtree and returns that node
- `TreeWalker.nextNode()`: moves the pointer to the next node in the subtree and returns that node

One common way to iterate through the subtree collection is with a `while` loop:

```js
const root = document.getElementById('tree-root');
const tw = document.createTreeWalker(root, NodeFilter.SHOW_ELEMENT);

const subTreeArray = [];
while (tw.nextNode()) {
  subTreeArray.push(tw.currentNode);
}

```

## Conclusion

TreeWalkers can be a powerful tool to traverse the DOM when used effectively.

---

Carlos Coves Prieto

02/14/2017

Career Path 3: Modern Frontend Developer
