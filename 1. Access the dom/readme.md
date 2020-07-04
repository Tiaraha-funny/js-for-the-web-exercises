Link : https://openclassrooms.com/fr/courses/5493201-write-javascript-for-the-web/5496631-get-access-to-the-dom

# document.getElementsByTagName()

One of the methods made available by the DOM for gaining access to elements is document.getElementsByTagName() . We pass the desired tag name to this method (e.g. "body," "h3," or "form") and it returns a collection of all of the elements within the DOM with that tag name.

Practice!
Head to CodePen Exercise P1CH2a and follow the instructions below.

This web page contains three articles inside <article> tags. In the JS editor, the constant articles contains a reference to a collection of all of these articles.

Use the constant paragraphs to store a reference to a collection of all <p> elements in the page.
The getElementsByTagName()method returns an HTMLCollection. You don't need to worry about exactly what that means: what is important is that we can gain access to a specific member of the collection in the same way we would do so with an Array. N.B. We cannot use Array methods like push() or indexOf() on HTMLCollection objects as they are not actual Array objects.

Copy and paste the following code into the JS editor:

const firstArticle = articles[0];
Using a similar method, create a constant called secondParagraph that stores a reference to the second paragraph element.

Once you've given it a go, watch me code a solution and see how your approach compares:

The program in my sandbox is formatted slightly differently than yours, but they both function with the same solution. 😉

# document.getElementsByClassName()

Similarly, we can access a collection of all elements with a certain class using the method document.getElementsByClassName() , passing it the class name we would like to access.

Practice!
Head to CodePen Exercise P1CH2b and follow the instructions below.
Both the page header and sidebar use the Bootstrap class text-white to, you guessed it, make the text inside them white.

Using the same logic as for getElementsByTagName(), try using getElementsByClassName() to store a reference to the collection of all elements with class text-white in a constant called whiteTextElements.

Once you've given it a go, watch me code a solution and see how your approach compares:

# document.getElementById()

One of the most useful DOM methods, document.getElementById() , returns the element with a given id . As you can see from the name of the method, it will only return one element — this makes sense, though, as in a correctly formatted HTML document, there will only ever be one element with a given id .

Practice!
Head to CodePen Exercise P1CH2c and follow the instructions below.

Look at the content in the HTML editor. As you can see, various elements have id attributes, such as the page header and the heading contained within it, the articles, and the sidebar.

In the JS editor, create a constant called sidebar and, using getElementById(), use it to store a reference to the <aside> element.

Once you've given it a go, watch me code a solution and see how your approach compares:

# document.querySelector()

The document.querySelector() method returns the first element in the DOM that matches the given selector(s). You can use tag names, classes, id attributes, or a mixture of the three:

document.querySelector('p') — returns the first <p> element

document.querySelector('.text-white') — returns the first element with class text-white

document.querySelector('#art-001') — returns the element with id attribute art-001

document.queryselector('p.text-white') — returns the first <p> element with class text-white

This method has a partner method, document.querySelectorAll() , which returns an NodeList containing all elements which match the given selector(s).
