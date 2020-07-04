Link : https://openclassrooms.com/fr/courses/5493201-write-javascript-for-the-web/5496636-modify-the-dom

# Modify the DOM

In the previous chapter, we learned that there are many ways of gaining access to specific elements, or groups of elements, within the DOM. Now that we have that access, what can we do?

# Modifying content

First and foremost, having access to DOM elements allows us to modify their content. For most cases, two properties suffice: innerHTML and textContent .

Practice!
Let's modify the page heading using JavaScript! Head to CodePen Exercise P1CH3a and follow the instructions below.

First things first: we need access to the heading. Using whichever DOM method you think best suited to the task, create a constant called mainHeading and assign to it a reference to the <h1> tag containing the page heading.

Now that we have a hold of the page's main heading, we're going to use its textContent property to modify what it says. Simply paste the following line of code just below your constant declaration: mainHeading.textContent = 'Modify the DOM'; . Let the sandbox refresh and check that it's working as expect.

But what if we want to make a larger modification, changing the <h1> tag to an <h2> tag, for example? Well, instead of using our reference to the heading itself, let's create a reference to the overall page <header>, and use its innerHTML property:

Use an appropriate method to assign a reference to the <header> element to a constant called header.

Paste the following line of code just underneath the header constant declaration:header.innerHTML = '<h2>Modify the DOM</h2>';. What happens when it refreshes? Not only has the heading gotten smaller, it has also aligned itself to the left of the header. This is because the original <h1> had class text-center, and we did not add that class to our new innerHTML. While it would be possible to simply add class="text-center" to our new innerHTML, we will see, in the next exercise, that there are easier and better ways of modifying an element's styles.

Once you've given it a go, watch me code a solution and see how your approach compares:

# A touch of class

Now that we can modify the content of our elements, let's have a look at how to modify their styles and attributes. Let's start with how to add and remove CSS classes using the classList property.

Practice!
Head to CodePen Exercise P1CH3b and follow the instructions below.

Let's start by getting that heading back in the center by applying the text-center class to its parent <header> element. Every element has a classList property, returning the class names applied to that element. However, classList is read-only, so we need to use its add() and remove() methods to modify the classes applied to an element.

Knowing that the required syntax is myElement.classList.add(className), add the text-center class to the <header> element.

Now the heading is sorted out, let's change the color of the sidebar. (A classList's remove() method has the same syntax as its add() method.) Using the sidebar constant we created earlier, replace the sidebar's bg-info class with bg-primary.

Once you've given it a go, watch me code a solution and see how your approach compares:

# Playing with style

What if we only want to modify one or two style attributes of an element? Instead of building classes for every possible requirement, we can use an element's style property to directly modify its styles.

Practice!
Head to CodePen Exercise P1CH3c and follow the instructions below.

Let's start by adding some padding to our <header> element, let's say 1em. Add the following line to the JavaScript in the JS editor: header.style.padding = '1em'; . You can change any CSS property of an element in this way. However, because the - operator is reserved in JavaScript, any property with a - in it will be slightly different, i.e. in camel case and without the -.

Using its classList property, remove the header's bg-dark class.

Set the header's background-color property to #B54135: header.style.backgroundColor = '#B54135'; .

Once you've given it a go, watch me code a solution and see how your approach compares:

# Building new elements

Now that we know how to modify existing elements, we can start building our own custom elements and adding them to the DOM. To create the element, we'll use document.createElement , and then we'll examine various ways of inserting it into the DOM.

Practice!
Head to CodePen Exercise P1CH3d and follow the instructions below.

The aim of the game here is to add a new <article> element to our page, after the three that currently exist. It will have a heading and a content paragraph, four Bootstrap classes and its id will be art-004. Let's break this down into simple steps.

First of all, we're going to use the createElement DOM method to build a new article element. Add the following line to the end of the JavaScript in the JS editor:

let newArticle = document.createElement('article');.

To populate this new article with a heading and a paragraph, create a new <h3> element and store it in a variable, and create a new <p> element and store it in a variable. These variables hold references to DOM elements, even though they do not yet appear in the DOM. We can therefore treat them as such, and use the methods we've been learning to add content.

Using each element's textContent property:

set the heading text to "Article 004,"

set the paragraph to any placeholder text you like.

Now we're going to use a new method, appendChild(), to add the heading and the paragraph to the <article> element. appendChild() adds an HTML element to a parent element, adding it after the parent's last child. Start by adding the heading to the article. If the variable containing your heading is called newHeading, the syntax will be:

newArticle.appendChild(newHeading);. Similarly, append the paragraph to newArticle.

The next step is to add the necessary classes to the new article. Using the new article's classList property, add the following four classes:

m-2

p-2

border

border-secondary

Hint: You can add multiple comma-separated classes with the classList.add() method.

We have one more attribute to add to our new article before adding it to the DOM: it needs an id. We're going to use a method we haven't come across yet to do so: setAttribute(). setAttribute() takes two arguments: the attribute you want to set, followed by the value you want to set for that attribute. Set newArticle's id attribute to art-004.

Now all that's left is to add it to the DOM! Using the methods you have learned so far, add the finished <article> element to the end of the <main> element, after the other articles. Don't forget to click Refresh to check everything worked!

Whew! 😅 Let's recap what we've done:

We created an <article> element.

We created heading and paragraph elements, populating them with their textContent properties.

We appended the heading and then the paragraph to the <article> element.

We added CSS classes and an id attribute.

We added newArticle to the DOM.

Once you've given it a go, watch me code a solution and see how your approach compares:
