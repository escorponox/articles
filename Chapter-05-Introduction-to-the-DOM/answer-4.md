#### Describe what the DOM is and explain its function.

# The JavaScript Document Object Model (DOM)

The DOM (Document Object Model) is a hierarchical tree model representing an HTML document. Its purposse is to serve as model which can be accessed to query or modify document's nodes dinamically.

## History
Web pages were initially static. Any little change had to be done with a full-page reload. As web pages complexity increased, a on-the-fly manipulating mechanism was required.

Back in the 90's, during the browser war between Netscape and Microsoft, the *level-0 DOM* and propietary versions of the DOM were launched by both companies. Propietary versions are known as *intermediate DOMs* nowadays and are not supported by actual browsers.

It was the World Wide Web Consortium ([W3C](https://www.w3.org/)) who recommended a standard known as "DOM Level 1" in 1998. This version was followed by "DOM Level 2" in late 2000 and "DOM Level 3" in April 2004. By 2005, W3C DOM was supported by most major to a large extent.

After passing through many hands, W3C published a draft of the "DOM Level 4", which is still under development.

## Level-0 DOM

*Level-0 DOM* or *Legacy DOM* provided access to a limited kind of elements in the document, namely *images*, *forms*, *links*, and *anchors*.

## W3C DOM in Modern Browsers

Current DOM versions are implemented in most modern browsers. Document's nodes are organized in a hierarchical tree model called *DOM tree*. These nodes can be accessed and manipulated with DOM methods providing advanced node selection, properties and display manipulation or keyboard and mouse event handling.

The browser parses the DOM and generates the web page. Scripting languages like JavaScript can access the DOM tree and modify its elements. This modifications will be reflected by the browser without reloading the whole page.

## Conclusion

The evolution of the DOM gave web pages interactive capabilities, which revolutioned web development.

---

Carlos Coves Prieto

07/05/2016

Career Path 3: Modern Frontend Developer