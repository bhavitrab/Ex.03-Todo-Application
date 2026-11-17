# Ex03 To-Do List using JavaScript
## Date:

## AIM
To create a To-do Application with all features using JavaScript.

## ALGORITHM
### STEP 1
Build the HTML structure (index.html).

### STEP 2
Style the App (style.css).

### STEP 3
Plan the features the To-Do App should have.

### STEP 4
Create a To-do application using Javascript.

### STEP 5
Add functionalities.

### STEP 6
Test the App.

### STEP 7
Open the HTML file in a browser to check layout and functionality.

### STEP 8
Fix styling issues and refine content placement.

### STEP 9
Deploy the website.

### STEP 10
Upload to GitHub Pages for free hosting.

## PROGRAM

<h1> index.html</h1>

```

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>My Todo Application</title>

    <link rel="stylesheet" href="./style.css">

    <script src="./new.js" defer></script>
</head>

<body>

    <div class="container">

        <!-- Header -->
        <header>
            <div class="logo">✓</div>

            <h1>My Todo List</h1>

            <p>Organize your daily tasks!</p>
        </header>


        <!-- Add Task Section -->
        <div class="input-section">

            <input
                type="text"
                id="taskInput"
                placeholder="Enter your task..."
                autocomplete="off"
            >

            <button id="addBtn">+ Add Task</button>

        </div>


        <!-- Task Statistics -->
        <div class="statistics">

            <div class="stat-box">
                <h2 id="totalCount">0</h2>
                <p>Total Tasks</p>
            </div>

            <div class="stat-box">
                <h2 id="pendingCount">0</h2>
                <p>Pending</p>
            </div>

            <div class="stat-box">
                <h2 id="completedCount">0</h2>
                <p>Completed</p>
            </div>

        </div>


        <!-- Filter Buttons -->
        <div class="filters">

            <button class="filter-btn active" data-filter="all">
                All
            </button>

            <button class="filter-btn" data-filter="pending">
                Pending
            </button>

            <button class="filter-btn" data-filter="completed">
                Completed
            </button>

        </div>


        <!-- Task List -->
        <div class="task-section">

            <h2>My Tasks</h2>

            <ul id="taskList"></ul>

            <p id="emptyMessage">
                No tasks yet. Add your first task!
            </p>

        </div>


        <!-- Bottom Section -->
        <div class="bottom-section">

            <p id="taskSummary">0 tasks remaining</p>

            <button id="clearBtn">
                Clear Completed
            </button>

        </div>

    </div>


    <!-- Student Details -->
    <footer>

        <p>Designed by: <strong>BHAVITRA B</strong></p>

        <p>Register Number: <strong>212225040047</strong></p>

        <p>Ex03 - To-Do List Using JavaScript</p>

    </footer>

</body>

</html>

```


<h1>style.css</h1>

```

/* General Styling */

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background: linear-gradient(135deg, #667eea, #764ba2);
    min-height: 100vh;
    padding: 40px 15px;
}


/* Main Container */

.container {
    max-width: 600px;
    margin: auto;
    background: white;
    padding: 30px;
    border-radius: 16px;
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
}


/* Header */

header {
    text-align: center;
    margin-bottom: 28px;
}

.logo {
    width: 55px;
    height: 55px;
    background: #667eea;
    color: white;
    font-size: 32px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto 15px;
}

header h1 {
    color: #333;
    font-size: 30px;
    margin-bottom: 10px;
}

header p {
    color: #888;
    font-size: 14px;
}


/* Input Section */

.input-section {
    display: flex;
    gap: 10px;
    margin-bottom: 25px;
}

.input-section input {
    flex: 1;
    min-width: 0;
    padding: 13px;
    border: 1px solid #ccc;
    border-radius: 7px;
    font-size: 14px;
    outline: none;
}

.input-section input:focus {
    border-color: #667eea;
}

button {
    border: none;
    border-radius: 7px;
    padding: 12px 15px;
    cursor: pointer;
    font-size: 13px;
    transition: 0.3s;
}

button:hover {
    opacity: 0.85;
}

#addBtn {
    background: #667eea;
    color: white;
}


/* Statistics */

.statistics {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
    margin-bottom: 25px;
}

.stat-box {
    background: #f1f1ff;
    text-align: center;
    padding: 18px 5px;
    border-radius: 9px;
}

.stat-box h2 {
    color: #667eea;
    font-size: 25px;
    margin-bottom: 5px;
}

.stat-box p {
    color: #777;
    font-size: 13px;
}


/* Filter Section */

.filters {
    display: flex;
    justify-content: center;
    gap: 10px;
    margin-bottom: 25px;
}

.filter-btn {
    background: #eee;
    color: #444;
    flex: 1;
}

.filter-btn.active {
    background: #667eea;
    color: white;
}


/* Task Section */

.task-section h2 {
    font-size: 20px;
    color: #333;
    margin-bottom: 18px;
}

#taskList {
    list-style: none;
}


/* Individual Task */

.task-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 10px;
    background: #f7f7fc;
    padding: 13px;
    border-radius: 8px;
    margin-bottom: 12px;
    border: 1px solid #eee;
}

.task-info {
    display: flex;
    align-items: center;
    gap: 10px;
    flex: 1;
    min-width: 0;
}

.task-checkbox {
    width: 18px;
    height: 18px;
    cursor: pointer;
    accent-color: #667eea;
    flex-shrink: 0;
}

.task-text {
    color: #444;
    font-size: 14px;
    overflow-wrap: anywhere;
}

.task-text.completed {
    text-decoration: line-through;
    color: #aaa;
}


/* Action Buttons */

.actions {
    display: flex;
    gap: 6px;
}

.edit-btn {
    background: #f0ad4e;
    color: white;
}

.delete-btn {
    background: #e74c3c;
    color: white;
}

.undo-btn {
    background: #667eea;
    color: white;
}


/* Empty Message */

#emptyMessage {
    text-align: center;
    color: #999;
    padding: 22px 5px;
    font-size: 14px;
}


/* Bottom Section */

.bottom-section {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 10px;
    margin-top: 22px;
    padding-top: 20px;
    border-top: 1px solid #eee;
}

#taskSummary {
    color: #777;
    font-size: 13px;
}

#clearBtn {
    background: #ffeded;
    color: #e74c3c;
}


/* Footer */

footer {
    text-align: center;
    color: white;
    margin-top: 30px;
    line-height: 1.9;
    font-size: 14px;
}


/* Responsive Design */

@media (max-width: 480px) {

    body {
        padding: 20px 10px;
    }

    .container {
        padding: 22px 15px;
    }

    header h1 {
        font-size: 25px;
    }

    .input-section {
        flex-direction: column;
    }

    #addBtn {
        padding: 13px;
    }

    .filters {
        gap: 5px;
    }

    .filter-btn {
        padding: 10px 5px;
        font-size: 12px;
    }

    .task-item {
        align-items: flex-start;
        flex-direction: column;
    }

    .actions {
        align-self: flex-end;
    }

    .bottom-section {
        flex-direction: column;
    }

}


```


<h1>new.js</h1>

```

// Get HTML Elements

const taskInput = document.getElementById("taskInput");
const addBtn = document.getElementById("addBtn");
const taskList = document.getElementById("taskList");

const totalCount = document.getElementById("totalCount");
const pendingCount = document.getElementById("pendingCount");
const completedCount = document.getElementById("completedCount");

const emptyMessage = document.getElementById("emptyMessage");
const taskSummary = document.getElementById("taskSummary");

const clearBtn = document.getElementById("clearBtn");
const filterButtons = document.querySelectorAll(".filter-btn");


// Load Tasks from Local Storage

let tasks = [];

try {
    const savedTasks = JSON.parse(localStorage.getItem("todoTasks"));

    if (Array.isArray(savedTasks)) {
        tasks = savedTasks;
    }

} catch (error) {
    tasks = [];
}

let currentFilter = "all";


// Save Tasks

function saveTasks() {

    localStorage.setItem("todoTasks", JSON.stringify(tasks));

}


// Add New Task

function addTask() {

    let text = taskInput.value.trim();

    if (text === "") {

        alert("Please enter a task!");

        return;

    }

    let newTask = {

        id: Date.now() + Math.random(),

        text: text,

        completed: false

    };

    tasks.push(newTask);

    taskInput.value = "";

    saveTasks();

    displayTasks();

    taskInput.focus();

}


// Add Task Using Enter Key

taskInput.addEventListener("keydown", function(event) {

    if (event.key === "Enter") {

        addTask();

    }

});


// Display Tasks

function displayTasks() {

    taskList.innerHTML = "";

    let filteredTasks = tasks.filter(function(task) {

        if (currentFilter === "pending") {

            return task.completed === false;

        }

        if (currentFilter === "completed") {

            return task.completed === true;

        }

        return true;

    });


    // Display Empty Message

    if (filteredTasks.length === 0) {

        emptyMessage.style.display = "block";

    } else {

        emptyMessage.style.display = "none";

    }


    // Create Task Elements

    filteredTasks.forEach(function(task) {

        let li = document.createElement("li");

        li.className = "task-item";


        // Task Information

        let taskInfo = document.createElement("div");

        taskInfo.className = "task-info";


        // Checkbox

        let checkbox = document.createElement("input");

        checkbox.type = "checkbox";

        checkbox.className = "task-checkbox";

        checkbox.checked = task.completed;

        checkbox.addEventListener("change", function() {

            toggleTask(task.id);

        });


        // Task Text

        let span = document.createElement("span");

        span.textContent = task.text;

        span.className = "task-text";

        if (task.completed) {

            span.classList.add("completed");

        }


        taskInfo.appendChild(checkbox);

        taskInfo.appendChild(span);


        // Action Buttons Container

        let actions = document.createElement("div");

        actions.className = "actions";


        // Edit Button

        let editBtn = document.createElement("button");

        editBtn.textContent = "Edit";

        editBtn.className = "edit-btn";

        editBtn.addEventListener("click", function() {

            editTask(task.id);

        });


        // Delete Button

        let deleteBtn = document.createElement("button");

        deleteBtn.textContent = "Delete";

        deleteBtn.className = "delete-btn";

        deleteBtn.addEventListener("click", function() {

            deleteTask(task.id);

        });


        // Append Buttons

        actions.appendChild(editBtn);

        actions.appendChild(deleteBtn);


        // Append Elements

        li.appendChild(taskInfo);

        li.appendChild(actions);

        taskList.appendChild(li);

    });


    updateStatistics();

}


// Mark Task as Completed

function toggleTask(id) {

    tasks.forEach(function(task) {

        if (task.id === id) {

            task.completed = !task.completed;

        }

    });

    saveTasks();

    displayTasks();

}


// Edit Task

function editTask(id) {

    let task = tasks.find(function(item) {

        return item.id === id;

    });

    if (!task) {

        return;

    }

    let updatedText = prompt("Edit your task:", task.text);

    if (updatedText === null) {

        return;

    }

    updatedText = updatedText.trim();

    if (updatedText === "") {

        alert("Task cannot be empty!");

        return;

    }

    task.text = updatedText;

    saveTasks();

    displayTasks();

}


// Delete Task

function deleteTask(id) {

    let confirmation = confirm("Are you sure you want to delete this task?");

    if (confirmation) {

        tasks = tasks.filter(function(task) {

            return task.id !== id;

        });

        saveTasks();

        displayTasks();

    }

}


// Filter Tasks

filterButtons.forEach(function(button) {

    button.addEventListener("click", function() {

        currentFilter = button.dataset.filter;

        filterButtons.forEach(function(btn) {

            btn.classList.remove("active");

        });

        button.classList.add("active");

        displayTasks();

    });

});


// Clear Completed Tasks

function clearCompleted() {

    let confirmation = confirm("Do you want to clear all completed tasks?");

    if (confirmation) {

        tasks = tasks.filter(function(task) {

            return task.completed === false;

        });

        saveTasks();

        displayTasks();

    }

}


// Update Statistics

function updateStatistics() {

    let total = tasks.length;

    let completed = tasks.filter(function(task) {

        return task.completed === true;

    }).length;

    let pending = total - completed;


    totalCount.textContent = total;

    pendingCount.textContent = pending;

    completedCount.textContent = completed;


    taskSummary.textContent = pending + " tasks remaining";

}


// Button Events

addBtn.addEventListener("click", addTask);

clearBtn.addEventListener("click", clearCompleted);


// Initial Display

displayTasks();

```
## OUTPUT
![alt text](<Screenshot 2026-11-17 124930.png>)

## RESULT
The program for creating To-do list using JavaScript is executed successfully.
