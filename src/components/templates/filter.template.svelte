<script lang="ts">
    import type { Tag } from "../molecules/tags.molecule.svelte";
    import Nav from "../organisms/nav.organism.svelte";
    import Posts from "../organisms/posts.organism.svelte";
    import type { ApiRef } from "../organisms/test.svelte";
    import Test from "../organisms/test.svelte";
    import NotFound from "./not-found.template.svelte";

    export let tagSlug: string;
    const tagsRef: ApiRef = {
        url: "https://api-eu-west-2.graphcms.com/v2/cl3ossjir6ju301z6grqwfdf9/master?query=query%20MyQuery%20%7B%0A%20%20tags%20%7B%0A%20%20%20%20label%0A%20%20%20%20url%0A%20%20%20%20blogPosts%20%7B%0A%20%20%20%20%20%20slug%0A%20%20%20%20%20%20title%0A%20%20%20%20%20%20content%20%7B%0A%20%20%20%20%20%20%20%20html%0A%20%20%20%20%20%20%20%20text%0A%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20tags%20%7B%0A%20%20%20%20%20%20%20%20label%0A%20%20%20%20%20%20%20%20url%0A%20%20%20%20%20%20%20%20blogPosts%20%7B%0A%20%20%20%20%20%20%20%20%20%20id%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%7D%0A%20%20%20%20%7D%0A%20%20%7D%0A%7D&operationName=MyQuery",
        queryName: "tags"
    }
    let tags: Tag[] = [];
    $: currTag = tags.find((tag) => tag.url == tagSlug);
    $: filteredTags = tags.filter((tag) => tag.url != currTag.url);
    $: isFound = currTag !== undefined;
</script>

<Test ref={tagsRef} bind:data={tags}>
    {#if isFound}
        <Nav label={`Filtered results for <em> ${currTag.label}</em>`} tagLabel="Filter: " tags={filteredTags}/>
        <Posts posts={currTag.blogPosts}/>
    {/if}

    {#if !isFound} <NotFound/> {/if}
</Test>