<script>
    let taskTitle = '';
    export let onAddTask;
  
    function submitForm() {
      if(taskTitle.trim()) {
        onAddTask({ title: taskTitle, completed: false });
        taskTitle = ''; // Reset
      }
    }
  </script>
  
  <div class="mb-3">
    <input type="text" bind:value={taskTitle} class="form-control" placeholder="Añade una nueva tarea" on:keyup="{event => event.key === 'Enter' && submitForm()}">
    <button class="btn btn-primary mt-2" on:click="{submitForm}">Añadir Tarea</button>
  </div>
  