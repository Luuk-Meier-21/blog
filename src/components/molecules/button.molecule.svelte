 
<script lang="ts">
    import Arrow from "../atoms/arrow.atom.svelte";

    export let text: string;
    export let href: string;
    export let area: string = "name";

    let areaVar = `--grid-area: ${area};`
</script>

<div class="return-button small" style={areaVar}>
    <a href={href} class="return-button__inner as-button"><Arrow/>{text}</a>
</div>

<style lang="scss">
    .return-button {
        position: relative;
    
        &__inner {
            position: fixed;
        }
    }
</style>