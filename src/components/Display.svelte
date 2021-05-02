<script>
    import { each } from "svelte/internal";

    import Picture from "./Picture.svelte";

    export let apiKey = 'DEMO_KEY';


	const fetchImage = (async () => {
		const response = await fetch(`https://api.nasa.gov/planetary/apod?api_key=${apiKey}`)
    return await response.json()
	})()

</script>

<style>
    .container {
        padding-bottom: 50px;
        display: flex;
        flex-direction: column;
        align-items: center;
    }
</style>

<div class="container">

{#await fetchImage}
	<p>...waiting</p>
{:then data}

{#if Array.isArray(data)}
    {#each data as dataset}
        <Picture dataset={dataset}/>
    {/each}
{:else}
    <Picture dataset={data}/>
{/if}

{:catch error}
	<p>An error occurred!</p>
{/await}

</div>