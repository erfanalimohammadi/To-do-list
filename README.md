# To-Do List Project

## Overview
This project is a simple To-Do List application that allows users to add and delete tasks. It uses HTML, CSS, and JavaScript, leveraging Bootstrap for styling and Font Awesome for icons.

## Features
- Add new tasks by typing into an input field and pressing Enter.
- Delete tasks by clicking on a trash icon next to each task.
- Responsive design for mobile and desktop users.

## Technologies Used
- HTML
- CSS
- JavaScript
- Bootstrap 4.5.2
- Font Awesome 4.7.0


## Installation and Usage

1. Clone the repository:
    
bash
    git clone [https://github.com/your-username/To-Do-List.git](https://github.com/erfanalimohammadi/To-do-list)
    cd To-Do-List
   

2. Open `index.html` in your web browser:
    
bash
    open index.html
   

## Code Explanation

### HTML (`index.html`)
The HTML file sets up the structure of the To-Do List application, including the input field for adding tasks and the list where tasks will be displayed.

``` html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <link rel="stylesheet" href="css/style.css" />
    <title>To-Do List</title>
  </head>
  <body>
    <div class="container">
      <ul class="list-group todos mx-auto text-light"></ul>
      <form class="add text-center my-4" autocomplete="off">
          <label class="text-light">Add New Todo...</label>
          <input type="text" class="form-control m-auto" name="add"/>
      </form>
    </div>
    <script src="js/script.js"></script>
  </body>
</html>
```
### CSS (`css/style.css`)
The CSS file provides styling for the To-Do List application, including background colors and layout adjustments.

``` css
body {
    background: #353f5b;
}
.container {
    max-width: 400px;
    margin-top: 90px;
}
.todos li {
    background: #423a6f;
}
.delete {
    cursor: pointer;
}
```
### JavaScript (`js/script.js`)
The JavaScript file contains the logic for adding and deleting tasks.

```javascript
let $ = document;
let inputElem = $.querySelector("input");
let addTodoForm = $.querySelector(".add");
let todoUlElem = $.querySelector(".todos");

function addNewTodo(newTodoValue) {
  let newTodoLi = $.createElement("li");
  newTodoLi.className =
    "list-group-item d-flex justify-content-between align-items-center";

  let newTodoTitleSpan = $.createElement("span");
  newTodoTitleSpan.innerHTML = newTodoValue;

  let newTodoTrash = $.createElement("i");
  newTodoTrash.className = "fa fa-trash-o delete";

  newTodoTrash.addEventListener("click", function (event) {
    event.target.parentElement.remove();
  });

  newTodoLi.append(newTodoTitleSpan, newTodoTrash);
  todoUlElem.append(newTodoLi);
}

addTodoForm.addEventListener("submit", function (event) {
  event.preventDefault();
});

inputElem.addEventListener("keydown", function (event) {
  let newTodoValue = event.target.value.trim();

  if (event.keyCode === 13) {
    if (newTodoValue) {
      inputElem.value = "";
      addNewTodo(newTodoValue);
    }
  }
});
```

## Contributing
If you would like to contribute to this project, please fork the repository and submit a pull request. 


