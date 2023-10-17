<script lang="ts">
    //let images: string[] = ["https://picsum.photos/200","https://picsum.photos/201","https://picsum.photos/202","https://picsum.photos/203"]
    export let src: string;
    let selected: number;
</script>
<main>
    <img src={src} alt="An anime face" />
    <select bind:value={selected} id="images" name="images">
        <option value="0" selected>Image A</option>
        <option value="1">Image B</option>
        <option value="2">Image C</option>
    </select>
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
        width: 20vw;
        height: 20vw;
        image-rendering: pixelated;
    }

    select {
        margin-top: 1rem;
        width: 10rem;
    }
</style>