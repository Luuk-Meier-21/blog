 
<script lang="ts">
    import Arrow from "../atoms/arrow.atom.svelte";

    export let text: string;
    export let href: string;
    export let area: string = "back";

    let areaVar = `--grid-area: ${area};`
</script>

<div class="home-button" style={areaVar}>
    <a href={href} class="home-button__inner"><Arrow/>{text}</a>
</div>

<style lang="scss">
    .home-button {
        position: relative;
        grid-area: var(--grid-area);
    
        &__inner {
            position: fixed;
        }
    }
</style>