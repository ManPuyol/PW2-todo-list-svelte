<script>
    import TaskForm from './TaskForm.svelte';
    import TaskList from './TaskList.svelte';
    let tasks = [];
    
    function addTask(task) {
    tasks = [...tasks, task];
  }

  function deleteTask(taskIndex) {
    tasks = tasks.filter((_, index) => index !== taskIndex);
  }

  function toggleComplete(taskIndex) {
    tasks = tasks.map((task, index) => {
      if(index === taskIndex) {
        return {...task, completed: !task.completed};
      }
      return task;
    });
  }
</script>

  
  <div class="container mt-5">
    <h1 class="text-center">Lista de Tareas</h1>
    <TaskForm on:addTask={addTask} />
    <TaskList {tasks} on:deleteTask={deleteTask} on:toggleComplete={toggleComplete} />
  </div>
  