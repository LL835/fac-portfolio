# Testing
## 1. Check that passing a given input into our tests returns the expected output

![Screenshot 2022-12-08 at 18 34 37](https://user-images.githubusercontent.com/104517597/206538526-58a3dcf4-b776-4de4-bb54-eb460e8552e9.png)


## 2. Write tests to mimic the behaviour of a user performing different actions

Test mimicking user adding a task to their to-do list:

```js
test("Can a user add a new task to the list?", () => {
  // 1. Create a new task
  const input = document.querySelector("#to-do");
  input.value = `This is a task`;
  const submitButton = document.querySelector("#submit-btn");
  submitButton.click();
// 2. Grab all the li elements in the DOM to see how many tasks have been created
const currentTasks = document.querySelectorAll(".listItem");
// 3. Check the length of the list;
NumOfTasks = currentTasks.length;
// 4. Compare the number of tasks in the DOM with the expected number
equal(NumOfTasks, 1);
// 5. Reset DOM 
const removeButtons = document.querySelectorAll(".remove-task-btn");
removeButtons.forEach(button => button.click())
})
```
## 3. Write testable, modular functions

We used separate functions for adding and removing tasks and controlling local storage.
```js
const getTasksFromLocalStorage = (task) => {
...
}

const addTaskItem = () => {
...
}

const deleteTask = (e) => {
...
}
```


## 4. Write functions that add, remove or modify DOM nodes

Function that removes task from to-do list:

```js
const deleteTask = (e) => {
  // uses .closest to remove 'closest li element'
  const taskToDelete = e.closest("li");
  // Gets the ID of the task to delete
  const uniqueID = taskToDelete.dataset.taskNum;
  // Use filter to remove (filter out) the task to remove and update the tasks array
  userTasks = userTasks.filter(item => item.id !== uniqueID);
  // Update the tasks array in local storage
  localStorage.setItem("userTasks", JSON.stringify(userTasks));
  // remove the task
  taskToDelete.remove();
};

```
## 5. Apply event listeners to HTML form elements

We used a "on click" event for the submit button:

```js
submitBtn.addEventListener("click", (e) => {
  e.preventDefault();
  addTaskItem();
});
```
But we could also have used a "submit" event for form instead.

## 6. Use scope to control what variables are accessible inside functions and blocks

The local storage array was a global variable: 
```js
let userTasks = JSON.parse(localStorage.getItem("userTasks")) || [];
```

Also used variables inside specific functions, e.g.:

```js
const markTaskAsComplete = (e) => {
  // uses .closest to find the 'closest li element'
  const selectedTask = e.closest("li");
  // Gets the ID of the task to delete
  const uniqueID = selectedTask.dataset.taskNum;
  // Find the item (which is an object) in the tasks array which has the same ID as the one clicked by user
  const index = userTasks.findIndex(item => item.id === uniqueID);

  // Update the object's completed status
  if (userTasks[index].completed === true){
    userTasks[index].completed = false;
  }
  else {
    userTasks[index].completed = true;
  }
  // Update the tasks array in local storage
  localStorage.setItem("userTasks", JSON.stringify(userTasks));
}
```

## 7. Use CSS grid to create complex layouts

We didn't use CSS grid for this project but I've used it in a take-home challenge.

```css
#calendar-grid {
    display: grid;
    max-width: 1300px;
    margin-left: auto;
    margin-right: auto;
    grid-template-columns: repeat(auto-fit, minmax(310px, 1fr));
    gap: 6px;
}
```

## 8. Use CSS grid to make layouts that adapt to the viewport size

See #7. But we did make the project adapt to viewport size.

![Screenshot 2022-12-01 at 17 24 51](https://user-images.githubusercontent.com/104517597/205119491-45d9c3fd-d0c5-4948-a690-ec001f33ee25.png)

![Screenshot 2022-12-01 at 17 27 12](https://user-images.githubusercontent.com/104517597/205120021-7cbfcaa4-936c-4484-9722-8fb643c88117.png)

