<script>
    export let answer = 'a mystery';
    let m = {x: 0, y: 0};
</script>

<p>The answer is {answer}</p>

{#if isNaN(+answer)}
    <input bind:value={answer} />
    <div on:pointermove={(e) => {
		m = { x: e.clientX, y: e.clientY };
	}}>
        The pointer is at {m.x} x {m.y}
    </div>
{/if}