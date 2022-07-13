<script lang="ts">
  import Button from './lib/Button.svelte';
  import Group from './lib/Group.svelte';
  import TextInput from './lib/TextInput.svelte';
  import Title from './lib/Title.svelte'
  import TodoList from './lib/TodoList.svelte';
  import { genrateRandomNumber } from './lib/utils';
  import type { Todo } from './types/todo.type';
  
  let newTodoText = '';
  let todos: Todo[] = [];

  function handleAddTodo(message: string) {
    todos = [...todos, { message, id: genrateRandomNumber(0, 9999999999999999999).toString() }]

    console.log(todos)
  }

  function handleRemoveTodo(id: string) {
    todos = todos.filter(t => t.id !== id);
  }
</script>

<main>
  <Title text='Todo App' />
  <Group>
    <TextInput bind:value={newTodoText} placeholder='Todo' />
    <Button onClick={() => handleAddTodo(newTodoText)}>Test</Button>
  </Group>
  <TodoList todos={todos} on:delete={e => {
    handleRemoveTodo(e.detail.id)
  }} />
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
      Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }

  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
  }
</style>
