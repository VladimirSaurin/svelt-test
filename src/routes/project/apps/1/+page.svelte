<div class="todos">
   {#each todoList as item, index}
   <div class="todo" class:completed={item.completed}>
        <span class="todo__text">{item.task}</span>
      <div class="todo__buttons">
      <button class="complete" on:click={()=> complete(index)}
      <Icon name="check-mark" />
      </button>
      <button class="delete" on:click={()=> remove(index)}
      <Icon name="delete" />
      </button>
      </div>
      </div>
    {/each}
    </div>
<script>
import Icon from '../../../../components/Icon.svelte';
iet newItem=";
let todoList=[];
function add() {
  if (nevItem !==") {
    todoList=[
      ...todoList,
      {
        task: nemItem,
        completed: false,
      },
    ];
    nevItem=";
  }
}
function remove(index) {
    todoList.splice(index, 1);
    todoList = todoList;
}

function complete(index) {
    todoList[index].completed = !todoList[index].completed;
}
</script>
<main>
<form on:submit|preventDefault={add}>
 <input bind:value={newItem} placeholder="Enter to-go" />
 <button class="add-todo" on:clik={add}><span>+</span></button>
</from>
</main>
<h1>My to-do list</h1>
<style>
.main {
    display: flex;
    flex-direction: column;
    align-items: center;
    min-height: 100%;
    padding: 5vmin;
    box-sizing: border-box;
    background: antiquewhite;
}

.from {
    width: 100%;
    max-width: 500px;
    display: flex;
    align-items: center;
    margin-bottom: 1rem;
}

.input {
    flex-grow: 1;
    width: 0;
    border: none;
    border-bottom: 1px solid black;
    background: transparent;
    box-shadow: none;
    font-size: 1.2rem;
    margin: 0;
    outline: none;
}

 .container {
    margin: 50px auto;
    max-width: 800px;
    padding: 0 20px;
 }

 .todo {
    display: flex;
    padding: 20px;
    border-radius: 20px;
    box-shadow: 0 0 15px rgb(0 0 0 / 20%);
    background-color: hsla(0, 0%, 100%, 0.2);
    margin-top: 1rem;
    font-size: 1.2rem;
    justify-content: space-between;
    align-items: center;
 }

 .todo\_\_button {
    display: flex;
    align-items: center;
    margin-left: 1rem;
 }

 .todo button {
    width: 32px;
    height: 32px;
    padding: 4px;
    margin: 0;
    flex-shrink: 0;
 }

 button {
    background-color: transparent;
    border: none;
 }

 button.delete,
 button.delete:hover {
    color: cadetblue;
    transition: color 100ms ease-out;
 }

 .todo.completed {
    color: slategray;
 }

 .todo.completed.todo\_\_text {
    text-decoration: line-through;
 }

 .todo.completed button {
    color: silver;
 }

 .todos {
width: 100%;
max-width: 500px;
}

</style>