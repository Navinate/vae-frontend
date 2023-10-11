<script lang="ts">
    import ImagePicker from "$lib/ImagePicker.svelte";
</script>

<main>
    <!--1st row-->
    <header></header>
    <!--2nd row-->
    <div />
    <ImagePicker />
    <div>arrow pointing down</div>
    <ImagePicker />
    <div />
    <!--3rd row-->
    <div />
    <div />
    <ImagePicker pickable={false} />
    <div />
    <div />

</main>

<style>
    main {
        display: grid;
        height: 100vh;
        grid-template-columns: 1fr repeat(3, 2.66fr) 1fr;
        grid-template-rows: 1fr 4fr 5fr;
    }

    header {
        grid-column: 1 / -1;
        grid-row: 1;
        background-color: #333;
    }
</style>