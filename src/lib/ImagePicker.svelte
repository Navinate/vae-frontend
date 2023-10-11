<script lang="ts">
    export let src: string = "https://picsum.photos/60";
    export let pickable: boolean = true;
    export let selected: number = 0;
</script>
<main>
    <img src={src} alt="An anime face" />
    {#if pickable}
        <select bind:value={selected} id="images" name="images">
            <option value="0">Image A</option>
            <option value="1">Image B</option>
            <option value="2">Image C</option>
            <option value="3">Image D</option>
            <option value="4">Image E</option>
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
        border-radius: 1rem;
        width: 100%;
        height: 100%;
        image-rendering: pixelated;
        box-shadow: 1rem 1rem 1rem black;
    }
</style>