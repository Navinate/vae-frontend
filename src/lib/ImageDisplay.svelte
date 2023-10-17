<script lang="ts">
    export let images: string[];
    let opacities: number[] = [];

    let value: number = 0;

    for(let i = 0; i < images.length; i++) {
        opacities.push(0);
    }

    function gaussian(x:number, a:number, b:number): number {
        let numerator = Math.pow(x - a, 2);
        let denominator = 2 * Math.pow(b, 2);
        return Math.exp(- numerator/ denominator);
        
    }

    $: {
        for(let i = 0; i < opacities.length; i++) {
            opacities[i] = Math.round(gaussian(value, i, 1)*100)/100;

        }
    }
</script>
<main>
    <input type="range" bind:value={value} min="0" max="9" step="0.1"/>
    <div class="img-stack">
        {#each images as image, i}
        <img src={image} alt="An anime face" style="opacity: {opacities[i]};" />
        {/each}
    </div>
    
</main>


<style>
    main {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        place-self: start center;
        gap: 2rem;
        width: 100%;
    }
    .img-stack {
        position: relative;
    }
    img {
        border-radius: 0.5rem;
        width: 20vw;
        margin-left: -10vw;
        height: 20vw;
        image-rendering: pixelated;
        position: absolute;
        opacity: .5;
    }

    input[type="range"] {
        width: 100%;
    }
</style>