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

<style lang="scss">
    .posts {
        grid-area: title;

        &__post {
            padding-top: var(--single);

            &:first-child {
                padding-top: unset;
            }
        }
    }
</style>