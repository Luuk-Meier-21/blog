<script lang="ts" context="module">
    import type { PostData } from "../organisms/post.organism.svelte";

    export interface Tag {
        label: string;
        url: string;
        blogPosts: PostData[];
    };
</script>

<script lang="ts">
    export let data: Tag[];
</script>

<ul class="tags list-horizontal">
    {#each data as tag, i}
        <li>
            <a href={`/filter/${tag.url}`}>{tag.label}</a>{(i < data.length - 1) ? ", " : ""}
        </li>
    {/each}
</ul>