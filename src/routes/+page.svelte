<script lang="ts">
	import ImageDisplay from "$lib/ImageDisplay.svelte";
    import ImagePicker from "$lib/ImagePicker.svelte";

    let gan: string[] = [];
    for(let i = 0; i < 10; i++) {
        gan.push(`/gan/${i}.png`);
    }
</script>

<main>
    <!--1st row-->
    <header>
        <h1>Anime Face Morpher</h1>
    </header>
    <!--2nd row-->
    <div />
    <ImagePicker src={gan[0]} />
    <div>
        <img src="/arrow_down_left.svg" alt="arrow pointing from left to down" />
        <img src="/arrow_down_right.svg" alt="arrow pointing from right to down" />
    </div>
    <ImagePicker src={gan[9]} />
    <div />
    <!--3rd row-->
    <div />
    <div />
    <ImageDisplay images={gan}/>
    <div />
    <div />

</main>

<style>
    main {
        display: grid;
        height: 100vh;
        grid-template-columns: 1fr repeat(3, 2.66fr) 1fr;
        grid-template-rows: 1fr 4fr 5fr;
        place-items: center;
        gap: 1rem;
    }

    header {
        grid-column: 1 / -1;
        grid-row: 1;
        background-color: #333;
        width: 100vw;
        height: 100%;
        color: white;
        display: grid;
        place-items: center;
        font-family: sans-serif;
    }

    img {
        width: 12vw;
    }
</style>