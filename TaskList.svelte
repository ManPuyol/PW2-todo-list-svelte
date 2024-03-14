<script>
    export let tasks;
    export let onDeleteTask;
    export let onToggleComplete;
  
    function handleDelete(index) {
      onDeleteTask(index);
    }
  
    function handleToggleComplete(index) {
      onToggleComplete(index);
    }
  </script>
  
  <ul class="list-group">
    {#each tasks as {title, completed}, index}
      <li class="list-group-item d-flex justify-content-between align-items-center">
        <span class="{completed ? 'text-decoration-line-through' : ''}">{title}</span>
        <div>
          <button class="btn btn-success btn-sm" on:click={() => handleToggleComplete(index)}>Completar</button>
          <button class="btn btn-danger btn-sm" on:click={() => handleDelete(index)}>Eliminar</button>
        </div>
      </li>
    {/each}
  </ul>
  