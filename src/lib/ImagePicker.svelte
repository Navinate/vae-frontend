<script lang="ts">
    let images: string[] = ["https://picsum.photos/200","https://picsum.photos/201","https://picsum.photos/202"]
    export let src: string | undefined = undefined;
    export let pickable: boolean = true;
    let selected: number = pickable ? 0 : -1;
</script>
<main>
    {#if !pickable}
        {#if src === undefined}
            <img src="/loading.svg" alt="loading" />
        {:else}
            <img src={src} alt="An anime face" />
        {/if}
    {:else}
        <img src={images[selected]} alt="An anime face" />
        <select bind:value={selected} id="images" name="images">
            <option selected value="1">Image A</option>
            <option value="2">Image B</option>
            <option value="3">Image C</option>
        </select>
    {/if}
</main>


<style>
    main {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        place-items: center;
    }
    img {
        border-radius: 0.5rem;
        width: 25vw;
        height: 25vw;
        image-rendering: pixelated;
    }

    select {
        margin-top: 1rem;
        width: 10rem;
    }
</style>