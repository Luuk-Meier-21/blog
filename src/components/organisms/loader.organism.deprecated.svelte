<script lang="ts" context="module">
    export interface ApiRef {
        url: string;
		contextName: string;
		queryName: string;
    };
</script>

<script lang="ts">
	import { setContext } from "svelte";
	import type { PostData } from "./post.organism.svelte";

	export let ref: ApiRef = {
		url: "https://api-eu-west-2.graphcms.com/v2/cl3ossjir6ju301z6grqwfdf9/master?query=query%20MyQuery%20%7B%0A%20%20blogPosts%20%7B%0A%20%20%20%20slug%0A%20%20%20%20title%0A%20%20%20%20tags%20%7B%0A%20%20%20%20%20%20label%0A%20%20%20%20%20%20url%0A%20%20%20%20%7D%0A%20%20%20%20content%20%7B%0A%20%20%20%20%20%20html%0A%20%20%20%20%20%20text%0A%20%20%20%20%7D%0A%20%20%7D%0A%7D",
		contextName: "posts",
		queryName: "blogPosts"
	}

	let data: any[] = [];

	const fetchPosts = (async () => {
		const response = await fetch(ref.url);
		const json = await response.json();
		
		data = json.data[ref.queryName];
	})();

	$: setContext(ref.contextName, data);
	console.log(data)
</script>

{#await fetchPosts}
    <p class="status-content">Looking for post...</p>
{:then data}
    <slot></slot>
{:catch error}
    <p class="status-content">An error occurred.</p>
{/await}