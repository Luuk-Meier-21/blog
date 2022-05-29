 
<script lang="ts">
    import Arrow from "../atoms/arrow.svelte";

    export let text: string;
    export let area: string = "name";

    let areaVar = `--grid-area: ${area};`
</script>

<div class="return-button small" style={areaVar}>
    <span class="return-button__inner"><Arrow/>{text}</span>
</div>

<style lang="scss">
    .return-button {
        position: relative;

        &__inner {
            position: fixed;
        }
    }
</style>