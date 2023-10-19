<script lang="ts">
	import ImageDisplay from "$lib/ImageDisplay.svelte";
    let images: string[] = [];
    for(let i = 0; i < 10; i++) {
        images.push(`https://picsum.photos/seed/${i}/200`);
    }

</script>
<main>
<ImageDisplay images={images}/>
</main>
<style>
    main {
        width: 50%;
        height: 100%;
        margin: auto;
        padding-top: 5rem;
    }
</style>