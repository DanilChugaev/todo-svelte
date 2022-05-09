<script>
    import InputText from "../components/InputText.svelte";

    let result = '';

    function handleMessage(event) {
        result = event.detail.value;
    }
</script>

<h1>It's my mini todo</h1>

<div class="wrapper">
    <InputText on:enter={handleMessage}/>

    {result}
</div>

<style>
    .wrapper {
        width: 100%;
        max-width: 400px;
    }
</style>
