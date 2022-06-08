

<script lang="ts">
    import { getContext } from "svelte";
    import Nav from "../organisms/nav.organism.svelte";
    import Post from "../organisms/post.organism.svelte";
    import NotFound from "./not-found.template.svelte";
    import type { PostData } from "../organisms/post.organism.svelte";

    export let postSlug: string;

    const posts: PostData[] = getContext('posts');
    $: currPost = posts.find((post) => post.slug == postSlug);
    $: isFound = currPost !== undefined;
</script>

{#if isFound}
    <Nav label="Luuk Meier" tags={currPost.tags}/>
    <Post data={currPost}/>
{/if}

{#if !isFound} <NotFound/> {/if}

<style lang="scss">
    
</style>
