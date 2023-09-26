<script lang="ts">
    import svelteLogo from './assets/svelte.svg';
    import viteLogo from '../public/vite.svg';
    import Counter from './lib/Counter.svelte';
    import Nested from './lib/Nested.svelte';
    import PackageInfo from './lib/PackageInfo.svelte';
    import ButtonColor from './lib/ButtonColor.svelte';
    import Thing from "./lib/Thing.svelte";
    import Image from "./lib/Image.svelte";
    import Inner from './lib/Inner.svelte';

    const pkg = {
        name: 'svelte',
        speed: 'blazing',
        version: 4,
        website: 'https://svelte.dev'
    };
    let yes = false;
</script>

<main>
    <div>
        <a href="https://vitejs.dev" target="_blank" rel="noreferrer">
            <img src={viteLogo} class="logo" alt="Vite Logo"/>
        </a>
        <a href="https://svelte.dev" target="_blank" rel="noreferrer">
            <img src={svelteLogo} class="logo svelte" alt="Svelte Logo"/>
        </a>
    </div>
    <h1>Vite + Svelte</h1>
    <label>
        <input type="checkbox" bind:checked={yes} />
        Do you want to show card ?
    </label>
    <button disabled={!yes}>Show card</button>

    <div class="card">
        <Counter/>
    </div>

    <div class="card">
        <Nested answer={42}/>
        <Nested/>
    </div>

    {#if yes}
        <div class="card">
            <ButtonColor/>
        </div>
    {/if}

    <div class="card">
        <Thing/>
    </div>

    {#if yes}
        <div class="card">
            <Image/>
        </div>
        <div class="card">
            <PackageInfo {...pkg}/>
        </div>
    {/if}

    <div class="card">
        <Inner on:message={(event) => alert(event.detail.text)}/>
    </div>

    <p>
        Check out <a href="https://github.com/sveltejs/kit#readme" target="_blank" rel="noreferrer">SvelteKit</a>, the
        official Svelte app framework powered by Vite!
    </p>

    <p class="read-the-docs">
        Click on the Vite and Svelte logos to learn more
    </p>
</main>

<style>
    .logo {
        height: 6em;
        padding: 1.5em;
        will-change: filter;
        transition: filter 300ms;
    }

    .logo:hover {
        filter: drop-shadow(0 0 2em #646cffaa);
    }

    .logo.svelte:hover {
        filter: drop-shadow(0 0 2em #ff3e00aa);
    }

    .read-the-docs {
        color: #888;
    }
</style>
