<script lang="ts">
    import PostLink from "../molecules/post-link.molecule.svelte";
    import type { PostData } from "./post.organism.svelte";

    export let posts: PostData[];
</script>

<ul class="posts">
    {#each posts as post}
        <li class="posts__post"><PostLink post={post}/></li>
	{/each}
</ul>

<style>
    .posts {
        grid-area: title;
    }
</style>