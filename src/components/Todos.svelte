<script lang="ts">
    import type { ITodo, ITodoUid, ITodoText } from "./types.ts";

    export let uid: ITodoUid = 0;
    export let text: ITodoText = '';
    let todos: ITodo[] = [];

    $: {
        if (uid && text) {
            todos.unshift({
                uid,
                text,
            });
            todos = todos;
        }
    }
</script>

<ul class="todo">
    {#each todos as todo (todo.uid)}
        <li>
            {todo.text}
        </li>
    {/each}
</ul>
