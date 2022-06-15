<script lang="ts" context="module">
    export interface ApiRef {
        url: string;
		queryName: string;
    };

    export interface ApiData {
        tags: Tag[];
        blogPosts: PostData[];
        images: ImageData[];
    }
</script>

<script lang="ts">
    import { setContext } from "svelte";
    import { gqlFetch, gqlQueryResolver } from "../../utilities/queries";
    import type { ImageData } from "../molecules/image.molecule.svelte";
    import type { Tag } from "../molecules/tags.molecule.svelte";
    import type { PostData } from "./post.organism.svelte";

	export let ref: ApiRef = {
		url: "https://api-eu-west-2.graphcms.com/v2/cl3ossjir6ju301z6grqwfdf9/master",
		queryName: "api"
	}

    let data: ApiData = {
        tags: [],
        blogPosts: [],
        images: []
    };

	const fetchPosts = (async () => {
        const response = await gqlFetch((q) => [
            q.tags,
            q.blogPosts,
            q.images
        ])
        const json = await response.json();
        console.log(json)
        data = json.data;
	})();

    $: setContext("api", data);
</script>

{#await fetchPosts}
    <p class="status-content">Looking for post...</p>
{:then data}
    <slot></slot>
{:catch error}
    <p class="status-content">An error occurred.</p>
{/await}