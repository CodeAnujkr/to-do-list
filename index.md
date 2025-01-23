````javascript

        // Variables for DOM elements
const taskInput = document.getElementById('taskInput');
const addTaskBtn = document.getElementById('addTaskBtn');
const taskList = document.getElementById('taskList');

// Add new task
addTaskBtn.addEventListener('click', function () {
    const taskText = taskInput.value.trim();

    if (taskText) {
        const li = document.createElement('li');
        
        li.innerHTML = `
            <span>${taskText}</span>
            <button class="edit-btn">Edit</button>
            <button>Delete</button>
        `;
        
        taskList.appendChild(td);

        // Clear input field
        taskInput.value = '';

        // Edit button functionality
        const editBtn = li.querySelector('.edit-btn');
        editBtn.addEventListener('click', function () {
            const newTask = prompt("Edit your task:", taskText);
            if (newTask && newTask.trim()) {
                li.querySelector('span').textContent = newTask;
            }
        });

        // Delete button functionality
        const deleteBtn = li.querySelector('button:not(.edit-btn)');
        deleteBtn.addEventListener('click', function () {
            taskList.removeChild(li);
        });
    } else {
        alert("Please enter a task.");
    }
});
````
````html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>To-Do List</h1>
        <input type="text" id="taskInput" placeholder="Add a new task">
        <button id="addTaskBtn">Add Task</button>

        <ul id="taskList"></ul>
    </div>
</body>
</html>


````