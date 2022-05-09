<script lang="ts">
    export let uid: number = 0;
    export let text: string = '';

    type Todo = {
        uid: number;
        text: string;
    };

    export let todos: Todo[] = [];

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

{#each todos as todo (todo.uid)}
    <p>
        {todo.text}
    </p>
{/each}
