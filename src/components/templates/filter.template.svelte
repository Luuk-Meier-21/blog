<script lang="ts">
    import type { Tag } from "../molecules/tags.molecule.svelte";
    import Nav from "../organisms/nav.organism.svelte";
    import Posts from "../organisms/posts.organism.svelte";
    import type { ApiData, ApiRef } from "../organisms/loader.organism.svelte";
    import Loader from "../organisms/loader.organism.svelte";
    import NotFound from "./not-found.template.svelte";
    import { getContext } from "svelte";

    export let tagSlug: string;

    const {tags, blogPosts} = getContext<ApiData>("api");
        console.log(tags)
        $: currTag = tags.find((tag) => tag.url == tagSlug);
        $: filteredTags = tags.filter((tag) => tag.url != currTag.url);
        $: isFound = currTag !== undefined;
</script>

{#if isFound}
    <Nav label={`Filtered results for <em> ${currTag.label}</em>`} tagLabel="Filter: " tags={filteredTags}/>
    <Posts posts={currTag.blogPosts}/>
{/if}

{#if !isFound} <NotFound/> {/if}