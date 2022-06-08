<script lang="ts" context="module">
    export interface Tag {
        label: string;
        url: string;
    };
</script>

<script lang="ts">
    export let data: Tag[];
    export let area: string = "tags";

    let areaVar = `--grid-area: ${area};`
    console.log(data)
</script>

<ul class="small tags list-horizontal" style={areaVar}>
    {#each data as tag, i}
        <li>
            <a href={`/filter/${tag.url}`}>{tag.label}</a>{(i < data.length - 1) ? ", " : ""}
        </li>
    {/each}
</ul>

<style>
    .tags {
        grid-area: var(--grid-area);
    }
</style>