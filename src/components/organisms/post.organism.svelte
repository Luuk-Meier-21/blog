<script lang="ts" context="module">
    import type { Tag } from "../molecules/tags.molecule.svelte";

    export interface PostData {
        slug: string;
        title: string;
        tags: Tag[];
        content: { 
            html: string;
            text: string;
        };
    };
</script>

<script lang="ts">
    export let data: PostData;
</script>

<h1 class="title">{data.title}</h1>
<article class="content">{@html data.content.html}</article>

<style lang="scss">
    .title {
        grid-area: title;
    }

    .content {
        grid-area: content;
    }
</style>
