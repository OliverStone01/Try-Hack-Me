# 🚪 Room: How Websites Work

## 🎯 Objectives
- To exploit a website, you first need to know how they are created.

## 💬 Summary
- How websites work
- HTML
- JavaScript
- Sensitive Data Exposure
- HTML Injection

---

## Notes

### Task 1 - How websites work
When you visit a website, your browser makes a request to a web server asking for information about the page you are trying to visiting. The server will respond with the data that your browser needs to display the page.
```
        -> Request from browser ->        -> Request from browser ->
[Browser]                        [Internet]                      [server]
        <- Response from server <-        <- Response from server <-
```

There are two major components that make up a website:
- **Front end (Client-side)** - the way your browser renders a website
- **Back end (Server-side)** - processes your request and returns a response.

-----

### Task 2 - HTML

Websites are primarily created using the following:
- **HTML** - Used to build the website structure and elements.
- **CSS** - Used to add styling to the site like background colours and other element styles.
- **JavaScript** - Used to implement iteractive elements and add funtionality to the website.

HTML = HyperText Markup Language

HTML is the language in which websites are written in. Elements (also known as tags) are the building blocks of HTML and they tell the browser how to display content.

Here is a little snipped of simple HTML:
```
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    <h1>Example Heading</h1>
    <p>Example Paragraph..</p>
  </body>
</html>
```

The HTML above has the following components:
- `<!DOCTYPE html>` defines that the page is HTML5 document. This helps with standardisation across different browsers.
- `<html>` is the root element of the of the HTML page. All other elements come after this element.
- `<head>` element contains information about the page such as the title.
- `<body>` defines the HTML document's body. Only content inside of the body will show in the browser.
- `<h1>` tag defines a large heading.
- `<p>` tag defines a paragraph.

tags can contain attributes such as the `class` attribute which can be used to style an element. An element can have multiple attributes each with its own unique purpose.

Elements can also have an id attribute `<p id="example">`. Elements must have a unique id. Id's are used for styling and to identify the element by JavaScript.

You can view the HTML of any site by right-clicking and selecting `view page source`.

-----

### Task 3 - JavaScript

JavaScript is one of the most popular coding languages. It allows pages to become interactive. JavaScript is used to control the functionality of the web page. 

JavaScript is added within the page source code and can be either loaded with `<script>` tags or can be included remotely with the src attribute: `<script src="/location/of/javascript_file.js"></script>`

The following JavaScript code finds a HTML element on the page with the id of `demo` and changes the element's contents to "hack the planet":
```
document.getElementById("demo").innerHTML = "Hack the planet";
```

HTML elements can also have events, such as `onclick` or `onhover` that executes JavaScript when the event occurs. The following code changes the text of the element with the demo id to button clicked:
```
<button onclick='document.getElementById("demo").innerHTML = "Button Clicked";'>Click Me!</button>
```

-----

### Task 4 - Sensitive data exposure

Sensitive data exposure occurs when a website doesn't properly protect sensitive clear-text information to the end-user.

A web developer may have forgotten to remove login credentials, hidden links to private parts of the website or other sensitive data shown in HTML or JavaScript.

Sensitive information can be potentially leveraged to further an attacker's access within different parts of a web application. for example, there could be HTML comments with temporary login credentials, and if you viewed the page's source code and found this, you could use these credentials to log in elsewhere on the application (or worse, used to access other backend components of the site).

Whenever you're assessing a web application for security issues, one of the first things you should do is review the page source code to see if you can find any exposed login credentials or hidden links.

-----

### Task 5 - HTML Injection

HTML injection is a vulnerability that that occurs when unfiltered user input is displayed or used for the functionality on the page. If a website fails to sanitise user input (filter any "malicious" text that a user inputs), and that input is used on the page, an attacker can inject HTML code into a vulnerable site.

Input sanitisation is very important in keeping a website secure, as information a user inputs into a website is often used in other frontend and backend functionality. Another vulnerability we will look at later is database injection, where we can manipulate a database lookup query to log in as another user by controlling the input that's directly used in the query - but for now, let's focus on HTML injection (which is client-side).

The general rule is never to trust user input.


-----

## Questions and Answers

### Task 1 

**q1.** What term best describes the component of a web application rendered by your browser?

Answer = Front end

-----

### Task 2

**q1.** First click the "View Site" button inside this task. On the right-hand side, you should see a box that renders HTML - If you enter some HTML into the box and click the green "Render HTML Code" button, it will render your HTML on the page; you should see an image of some cats.

Answer = No answer needed


**q2.** One of the images on the cat website is broken - fix it, and the image will reveal the hidden text answer!

Answer = HTMLHERO


**q3.** Add a dog image to the page by adding another img tag (<img>) on line 11. The dog image location is img/dog-1.png. What is the text in the dog image?

Answer = DOGHTML

-----

### Task 3

**q1.** Click the "View Site" button on this task. On the right-hand side, add JavaScript that changes the demo element's content to "Hack the Planet"

Answer = JSISFUN


**q2.** Add the button HTML from this task that changes the element's text to "Button Clicked" on the editor on the right, update the code by clicking the "Render HTML+JS Code" button and then click the button.

Answer = No answer needed

-----

### Task 4

**q1.** View the website on this link. What is the password hidden in the source code?

Answer = testpasswd

-----

### Task 5

**q1.** View the website on this task and inject HTML so that a malicious link to http://hacker.com is shown.

Answer = HTML_INJ3CTI0N

-----

