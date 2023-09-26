<script>
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();

    function sayHello() {
        dispatch('message', {
            text: 'Hello Marou!'
        });
    }
</script>

<button on:click={sayHello}>
    Click to say hello
</button>