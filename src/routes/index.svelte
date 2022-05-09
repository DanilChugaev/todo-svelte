<script>
    import InputText from "../components/InputText.svelte";
    import Todos from "../components/Todos.svelte";

    const todo = {
        text: '',
        uid: 0,
    };

    function handleMessage(event) {
        todo.text = event.detail.value;
        todo.uid = todo.uid + 1;
    }
</script>

<h1>It's my mini todo</h1>

<div class="wrapper">
    <InputText on:enter={handleMessage}/>

    <Todos {...todo}/>
</div>

<style>
    .wrapper {
        width: 100%;
        max-width: 400px;
    }
</style>
