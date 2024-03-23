
To-Do List Web Application Documentation

This documentation provides an overview of the HTML, CSS, and JavaScript code that constitutes a To-Do List web application.

HTML Structure (index.html)
The HTML structure defines the layout and content of the web page.

Document Type Declaration: <!DOCTYPE html> declares the document type and version of HTML being used.
Root Element: <html lang="en"> defines the root element of the HTML document, specifying the language as English.
Head Section: Contains metadata and external resource links.
Meta tags specify character encoding, viewport settings, and compatibility.
Link tags reference external stylesheets and Font Awesome CSS.
Title tag sets the title of the document.
Body Section: Contains visible content of the web page.
Containers for the title, input field, and list of tasks.
Use of semantic HTML elements such as <div>, <h1>, and <textarea>.
Integration of Font Awesome icons for buttons.

CSS Styling (style.css)


The CSS file provides styles for enhancing the appearance and layout of the web page.

Universal Reset: Resets margins, paddings, and box-sizing for consistency.
Body Styling: Sets background gradient and margins for the body content.
Container Title: Styles the title of the To-Do List container.
Container: Styles the input field and button, including dimensions, borders, and hover effects.
To-Do List Items: Defines styles for task items, check button, and trash button, along with hover effects and checked item styling.
Media Queries: Adjusts styles for smaller screens to maintain responsiveness.

JavaScript Functionality (script.js)

The JavaScript file adds interactivity and functionality to the web page.

Variable Declarations: Selects HTML elements for input, button, and task list.
Event Listeners: Listens for click events on the add button and task list.
Function Declarations:
clickButton(e): Adds a new task when the add button is clicked.
addTodo(): Creates a new task item and appends it to the task list.
okdel(e): Handles checking and deletion of tasks.
DOM Manipulation: Dynamically creates and modifies HTML elements based on user interactions.
CSS Class Toggling: Toggles CSS classes for checked items.
Button Click Handling: Identifies clicked buttons and performs corresponding actions.
Conclusion
This To-Do List web application combines HTML, CSS, and JavaScript to create a user-friendly interface for managing tasks. The HTML structure defines the layout, CSS provides visual styling, and JavaScript adds functionality for adding, checking, and deleting tasks. Together, these components form a responsive and interactive application for organizing to-do items.




To-Do List Web Application Documentation

Introduction
This documentation outlines the structure, styling, and functionality of a To-Do List web application. The application allows users to add, check, and delete tasks, providing an intuitive interface for task management.

1. HTML Structure (index.html)
The HTML file defines the layout and content structure of the web page.

html Code

<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Meta tags, title, external resources -->
</head>
<body>
    <!-- Container for title -->
    <div class="container-title">
        <h1>To Do List</h1>
    </div>

    <!-- Container for input field -->
    <div class="container">
        <div class="inputcol">
            <textarea name="text" class="textarea"></textarea>
            <button type="button" class="buttoninput">
                <i class="fa-solid fa-check ms-2"></i>
            </button>
        </div>
    </div>

    <!-- Container for displaying tasks -->
    <div class="todolist"></div>
</body>
</html>

Explanation:
The HTML structure comprises containers for the title, input field, and list of tasks.
The title container (container-title) displays the heading "To Do List".
The input field container (container) contains a textarea for entering tasks and a button for adding tasks.
The list container (todolist) is initially empty and will be populated with tasks dynamically.
2. CSS Styling (style.css)
The CSS file provides styles for enhancing the appearance and layout of the web page.

css code : 

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Times New Roman", Times, serif;
}

body {
  background-image: linear-gradient(to right, #605e7e, #6b73c1, #37b3cc);
  margin: 50px 2%;
}

/* container title */
.container-title {
  font-size: 25px;
  text-align: center;
  margin: 0 0 30px 0;
  color: white;
  text-shadow: 3px 1px black;
}

/* container */
.inputcol {
  display: grid;
  column-gap: 5px;
  grid-template-columns: 60% 10%;
  justify-content: center;
  margin-top: 10px;
}

.textarea {
  min-height: 50px;
  height: 50px;
  max-width: 100%;
  min-width: 100%;
  border-radius: 10px;
  border-color: #333;
  font-size: 20px;
  padding: 10px 10px;
  overflow: auto;
  overflow-x: hidden;
}

.textarea::-webkit-scrollbar-track {
  border-radius: 10px;
  background-color: #333;
}

.textarea::-webkit-scrollbar {
  width: 10px;
  cursor: pointer;
}

.textarea::-webkit-scrollbar-thumb {
  border-radius: 10px;
  background-color: #8f8acc;
  cursor: pointer;
}

.textarea:focus {
  outline: none;
}

.buttoninput {
  border-radius: 10px;
  border-color: #333;
  background-color: white;
  font-size: 20px;
}

.buttoninput:hover {
  background-color: #8f8acc;
  color: white;
}

/* js */
.todolist {
  margin-top: 20px;
}

.itemall {
  display: grid;
  grid-template-columns: 60% 5% 5%;
  justify-content: center;
  margin-bottom: 2px;
}

.item,
.check-button,
.trash-button {
  border: none;
  background-color: white;
  min-height: 50px;
  padding: 10px 10px;
}

.item {
  word-wrap: break-word;
  word-break: break-all;
  border-radius: 10px 0 0 10px;
  display: grid;
  align-content: center;
  font-size: 20px;
}

.check-button,
.trash-button {
  font-size: 15px;
}

.trash-button {
  border-radius: 0 10px 10px 0;
}

.check-button:hover {
  background-color: #37b3cc;
  color: white;
}

.trash-button:hover {
  background-color: #6b73c1;
  color: white;
}

.checklist {
  text-decoration: line-through;
}

.fa-check,
.fa-trash {
  pointer-events: none;
}

button,
.check-button,
.trash-button {
  cursor: pointer;
}

@media screen and (max-width: 768px) {
  .inputcol {
    grid-template-columns: 90% 10%;
  }

  .buttoninput {
    width: 100%;
    font-size: 15px;
  }
  .container-title {
    font-size: 18px;
    text-align: center;
    margin: 0 0 30px 0;
    color: white;
    text-shadow: 3px 1px black;
  }

  /* container */
  .inputcol {
    display: grid;
    column-gap: 3px;
    grid-template-columns: 70% 10%;
    justify-content: center;
    margin-top: 10px;
  }

  .textarea {
    min-height: 50px;
    height: 50px;
    max-width: 100%;
    min-width: 100%;
    border-radius: 10px;
    border-color: #333;
    font-size: 17px;
    padding: 10px 10px;
    overflow: auto;
    overflow-x: hidden;
  }

  .itemall {
    display: grid;
    grid-template-columns: 60% 5% 5%;
    justify-content: center;
    margin-bottom: 2px;
  }

  .check-button,
  .trash-button {
    border: none;
    background-color: white;
    min-height: 50px;
    padding: 1px 1px;
    padding-right: 30px;
  }
  .check-button,
  .trash-button {
    font-size: 16px;
    align-content: center;
    justify-content: center;
  }
  .item {
    word-wrap: break-word;
    word-break: break-all;
    border-radius: 10px 0 0 10px;
    display: grid;
    align-content: center;
    font-size: 17px;
  }

  .trash-button {
    border-radius: 0 10px 10px 0;
  }

  .checklist {
    text-decoration: line-through;
  }

  .fa-check,
  .fa-trash {
    pointer-events: none;
  }
  .trash-button {
    border-radius: 0 10px 10px 0;
  }
  .itemall {
    grid-template-columns: 80% 10% 10%;
  }

  .check-button {
    font-size: 16px;
    padding: 1%;
  }
  .trash-button {
    font-size: 16px;
    padding: 1%;
  }
}

Explanation:
The CSS file contains styles for resetting default browser styles, setting background colors, fonts, margins, padding, and other visual enhancements.
Styles are applied to elements such as containers, titles, input fields, buttons, and task items to ensure a visually appealing and consistent layout.
3. JavaScript Functionality (script.js)
The JavaScript file adds interactivity and functionality to the web page.

javascript Code :

const inputtdl = document.querySelector('.textarea')
const buttontdl = document.querySelector('.buttoninput')
const listtdl = document.querySelector('.todolist')

function clickButton(e) {
    e.preventDefault()
    addTodo()
}

// adding todoList
function addTodo() {
    const itemall = document.createElement('div')
    itemall.classList.add('itemall')

    const item = document.createElement('p')
    item.classList.add('item')
    item.innerText = inputtdl.value
    itemall.appendChild(item)

    if (inputtdl.value === '') return

    const checkbutton = document.createElement("button")
    checkbutton.innerHTML = '<i class="fa-solid fa-check"></i>'
    checkbutton.classList.add("check-button")
    itemall.appendChild(checkbutton)

    const trashbutton = document.createElement("button")
    trashbutton.innerHTML = '<i class="fa-solid fa-trash"></i>'
    trashbutton.classList.add("trash-button")
    itemall.appendChild(trashbutton)

    listtdl.appendChild(itemall)
    inputtdl.value = ''
}

// checking and delete todoList 
function okdel(e) {
    const item = e.target

    // check
    if (item.classList[0] === 'check-button') {
        const todolist = item.parentElement
        todolist.classList.toggle('checklist')
    }

    // delete
    if (item.classList[0] === 'trash-button') {
        const todolist = item.parentElement
        todolist.remove()
    }
}

buttontdl.addEventListener('click', clickButton)
listtdl.addEventListener('click', okdel)

Explanation:
JavaScript code handles user interactions, such as adding, checking, and deleting tasks.
Event listeners are used to detect user actions, such as button clicks.
Functions are defined to perform specific tasks, such as adding a new task or checking a task.
DOM manipulation is utilized to dynamically update the HTML content based on user actions.
Conclusion
The To-Do List web application combines HTML, CSS, and JavaScript to provide users with an intuitive interface for managing tasks. The HTML structure defines the layout, CSS enhances the visual appearance, and JavaScript adds functionality and interactivity. Together, these components create a seamless user experience for organizing and managing to-do items.









