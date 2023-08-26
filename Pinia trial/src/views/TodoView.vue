<template>
    <div class="app-container">
      <h1>TodoApp</h1>
      <div class="add-task">
        <input v-model="newTask" @click.enter="addTask" placeholder="Add a new task..." />
        <button @click="addTask">Save</button>
      </div>
      <ul class="todo-list">
        <li v-for="(task, index) in tasks" :key="index" :class="{'todo-item': true, 'completed': task.completed}">
          <div class="task-name">{{ task.name }}</div>
          <div class="task-time">{{ task.time }}</div>
          <button
            class="complete-button"
            :class="{'completed-button': task.completed}"
            @click="toggleCompletion(index)"
          >
            {{ task.completed ? 'Completed' : 'Complete' }}
          </button>
          <button class="delete-button" @click="deleteTask(index)">Delete</button>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        tasks: [],
        newTask: ""
      };
    },
    methods: {
      toggleCompletion(index) {
        this.tasks[index].completed = !this.tasks[index].completed;
      },
      addTask() {
        if (this.newTask.trim() !== "") {
          this.tasks.push({
            name: this.newTask,
            time: "Now",
            completed: false
          });
          this.newTask = "";
        }
      },
      deleteTask(index) {
        this.tasks.splice(index, 1);
      }
    }
  };
  </script>
  
  <style scoped>
.app-container {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  font-family: Arial, sans-serif;
}

.add-task {
  display: flex;
  margin-bottom: 20px;
}

.add-task input {
  flex-grow: 1;
  padding: 8px;
  font-size: 14px;
  border: 1px solid #ccc;
  border-radius: 4px 0 0 4px;
}

.add-task button {
  padding: 8px 15px;
  font-size: 14px;
  background-color: #007bff;
  border: none;
  border-radius: 0 4px 4px 0;
  color: #fff;
  cursor: pointer;
  transition: background-color 0.3s ease-in-out;
}

.add-task button:hover {
  background-color: #0056b3;
}

.todo-list {
  list-style-type: none;
  padding: 0;
}

.todo-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border: 1px solid #ccc;
  padding: 10px;
  margin-bottom: 10px;
  
}

.todo-item.completed {
  background-color: #f0f0f0;
}

.task-name {
  flex-grow: 1;
  margin-right: 10px;
}

.task-time {
  font-size: 12px;
  color: #888;
}

.complete-button, .delete-button {
  padding: 5px 10px;
  font-size: 14px;
  cursor: pointer;
  border: none;
  
}

.complete-button {
  background-color: #007bff;
  width: 100px;
  color: #fff;
}

.delete-button {
  background-color: #dc3545;
  color: #fff;
}

.completed-button {
  background-color: #28a745;
}

.complete-button:hover, .delete-button:hover {
  background-color: #0056b3;
}

.completed-button:hover {
  background-color: #218838;
}

</style>
  