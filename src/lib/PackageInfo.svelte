<script>
    export let name;
    export let version;
    export let speed;
    export let website;

    $: href = `https://www.npmjs.com/package/${name}`;

    import { getRandomNumber } from '../services/utils.js';

    let promise = getRandomNumber();

    function handleClick() {
        promise = getRandomNumber();
    }
</script>

<p>
    The <code>{name}</code> package is {speed} fast. Download version {version} from
    <a {href}>npm</a> and <a href={website}>learn more here</a>
</p>

<button on:click={handleClick}>
    generate random number
</button>

{#await promise}
    <p>...waiting</p>
{:then number}
    <p>The number is {number}</p>
{:catch error}
    <p style="color: red">{error.message}</p>
{/await}