<script lang='ts'>
    import type { Todo } from "src/types/todo.type";
    import { createEventDispatcher } from "svelte";
    import Button from "./Button.svelte";
    import Group from "./Group.svelte";

    export let todos: Todo[] = [];

    const dispatch = createEventDispatcher();
    
    function onRemoveTodo(id: string) {
        dispatch('delete', { id });
    }
</script>

<ul>
    {#each todos as { id, message }}
        <li>
            <Group>
                {message}
                <Button onClick={() => onRemoveTodo(id)}>Remove</Button>
            </Group>
        </li>
    {/each}
</ul>
  
<style>
    div {
        display: flex;
        flex-direction: column;
    }
</style>