<script>
    let things = [
        { id: 1, name: 'apple' },
        { id: 2, name: 'banana' },
        { id: 3, name: 'carrot' },
        { id: 4, name: 'doughnut' },
        { id: 5, name: 'egg' }
    ];

    const emojis = {
        apple: '🍎',
        banana: '🍌',
        carrot: '🥕',
        doughnut: '🍩',
        egg: '🥚'
    };
    function handleClick() {
        things = things.slice(1);
    }
</script>

<button on:click={handleClick}>
    Remove first thing
</button>

{#each things as thing (thing.id)}
    <p>{emojis[thing.name]} = {thing.name}</p>
{/each}
