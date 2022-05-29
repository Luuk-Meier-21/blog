<script lang="ts">
    export let text: string;
    export let area: string = "name";

    let areaVar = `--grid-area: ${area};`
</script>

<p class="post-name small" style={areaVar}>
    {text}
</p>

<style>
    .post-name {
        grid-area: var(--grid-area);
    }
</style>