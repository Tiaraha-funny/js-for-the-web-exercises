link : https://openclassrooms.com/fr/courses/5493201-write-javascript-for-the-web/5496641-listen-for-events

# Something happened in the DOM...

...now what? We want our users to be able to interact with our content by reacting to DOM events. When a user clicks a button, types in a text field or selects an option in a dropdown menu, an event is triggered, and by listening for that event, we can execute code to react to it.

In this chapter, we are going to build a mini app to learn about event handling and to practice everything we've covered in this part of the course. First of all, let's look at how to listen for an event, and how to react to it.

What is an event?
Here are a few examples of HTML events we can listen for:

the user clicks the element

the user moves the mouse over the element

the user presses a key

a form is submitted

the content of a form input is changed

Many of these events come with payloads: information about the event. For example, when a user clicks an element, one piece of information we receive is the X and Y coordinates of where the user clicked.

Let's have a look at how to react to these events.

# addEventListener()

We react to an event emitted by a DOM element by adding an event listener to that element. A listener is a function that will be executed every time the chosen event is emitted. The addEventListener() method takes two arguments: the event to listen for and the function to be executed when that event is emitted. Let's start with an example: adding a click listener to a button.

Practice!
Head to CodePen Exercise P1CH4a and follow the instructions below.

Here is the mini app we're going to build.

the four buttons under the page heading will change the background color of the <header> element by adding and removing classes

the Add Post button will add a new blog post with dummy content

the Remove Last Post button will remove all but one post.

Let's start with the buttons for the <header>.

First we need access to the <header> element. Using the methods you've learned, store a reference to the <header> element in a constant called header.

Now create a reference to the button marked "Blue" and store it in a constant called blueButton.

Similarly, store references to the other three buttons in constants called brownButton, greenButton and noneButton.

Now we're going to listen for blueButton's click event, and react to it by adding two classes to the header, all using the addEventListener() method.

Add the following to the end of the JS editor:

blueButton.addEventListener('click', () => { header.classList.add('blue-background', 'text-white');});
When the sandbox refreshes, click the Blue button to see what happens.

But hang on a minute: what happens if the user has already clicked on a button? We'd best make sure we remove any other color classes.

Inside blueButton's click listener, add this line:

header.classList.remove('brown-background', 'green-background');. That way, if another background has already been added, it will be removed to make sure there aren't conflicting CSS classes.

Now that you've got the idea, try and do the same for the Brown and Green buttons:

Add a click listener to brownButton which adds and removes the appropriate classes.

Add a click listener to greenButton which adds and removes the appropriate classes.

Our three color-changing buttons now work properly. Can you work out how the None button should work? Add a click listener to noneButton which will revert the header's colors to default.

Changing the styles of a web page with buttons is a fun example of event handling, but is not, perhaps, something we will use very often. Now let's look at implementing the Add Post button.

Practice!
Head to CodePen Exercise P1CH4b and follow the instructions below.

First of all, we're going to allow the user to add a new post. For now, the post will be hard-coded, but we can easily imagine capturing the data from a form and sending it to a server — you will learn how to do both before the end of this course.

Start by creating a function called createNewPost() which will return an HTML element of the same type as the post currently on the page: an <article> with class list-group-item, containing an <h5> heading and <p> content paragraph.

Add a listener to the Add Post button which runs createNewPost() and adds the resulting post to the DOM after the previous post and before the buttons.

When your sandbox refreshes, test your listener!

Once you've given it a go, watch me code a solution and see how your approach compares:

All that's left is to implement the Remove Last Post button, but let's add a twist!

Practice!
Head to CodePen Exercise P1CH4c and follow the instructions below.

Time for a challenge!

The "Remove Last Post" button should, as it says, remove the last added post but it should not affect the original post, leaving it intact.

HINT: HTML elements have a childElementCount property… 🤔😉
