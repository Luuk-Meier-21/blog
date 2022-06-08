
<script lang="ts">
	import { setContext } from "svelte";
	import type { PostData } from "../organisms/post.organism.svelte";

	let posts: PostData[] = [];

	export const fetchPosts = (async () => {
		const apiUrl = "https://api-eu-west-2.graphcms.com/v2/cl3ossjir6ju301z6grqwfdf9/master?query=query%20MyQuery%20%7B%0A%20%20blogPosts%20%7B%0A%20%20%20%20slug%0A%20%20%20%20title%0A%20%20%20%20tags%20%7B%0A%20%20%20%20%20%20label%0A%20%20%20%20%20%20url%0A%20%20%20%20%7D%0A%20%20%20%20content%20%7B%0A%20%20%20%20%20%20html%0A%20%20%20%20%20%20text%0A%20%20%20%20%7D%0A%20%20%7D%0A%7D";
		const response = await fetch(apiUrl);
		const json = await response.json();
		
		posts = json.data.blogPosts
    	return posts;
	})();

	$: setContext('posts', posts);
</script>

{#await fetchPosts}
    <p class="status">Looking for post...</p>
{:then posts}
    <slot></slot>
{:catch error}
    <p class="status">An error occurred.</p>
{/await}

<style>
	.status {
		grid-area: content;
	}
</style>