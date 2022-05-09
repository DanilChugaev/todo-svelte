<script>
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();

    let value = '';

    /**
     * Handle enter key from input field
     *
     * @param {KeyboardEvent} event
     * @returns {void}
     */
    function handleEnter(event) {
        if (event.code === 'Enter') {
            dispatch('enter', {value});
            clearValue();
        }
    }

    /**
     * Clear text in input field
     *
     * @returns {void}
     */
    function clearValue() {
        value = '';
    }
</script>

<input
        class="input-text"
        type="text"
        bind:value={value}
        on:keypress={handleEnter}
>

<style>
    .input-text {
        width: 100%;
    }
</style>
