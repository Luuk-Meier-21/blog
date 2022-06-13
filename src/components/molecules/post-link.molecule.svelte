<script lang="ts">
    import Arrow from "../atoms/arrow.atom.svelte";
    import type { PostData } from "../organisms/post.organism.svelte";
    import type { Tag } from "./tags.molecule.svelte";

    const truncateToCount = (str: string, wordCount: number) => str.replace(/\s+/g," ").split(/(?=\s)/gi).slice(0, wordCount).join('');

    export let post: PostData;


</script>

<a class="post-link is--hoverable" href={`/posts/${post.slug}`}>
    <h2 class="post-link__title">
        {post.title}<Arrow weight="bold" direction="right"/>
    </h2>
    <p class="post-link__snippet">{`${truncateToCount(post.content.text, 10)}...`}</p>
</a>

<style lang="scss"> 
    .post-link {

        display: block;
        // box-shadow: 0px 1px 0px 0px var(--color);

        &__title {
            display: flex;
            justify-content: space-between;
        }

        &__snippet {
            display: inline-block;
        }
    }
</style>