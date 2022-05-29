<script lang="ts">
	import Grid from "./components/molecules/grid.svelte";
	import Tags from "./components/molecules/tags.svelte";
	import type { Tag } from "./components/molecules/tags.svelte";
	import PostName from "./components/molecules/post-name.svelte";
import ReturnButton from "./components/molecules/return-button.svelte";
	
	export let name: string;

	const postName = "Test"
	const tags: Tag[] = [
		{
			label: "test",
			url: "",
		},
		{
			label: "test",
			url: "",
		},
		{
			label: "test",
			url: "",
		}
	]

</script>

<main>
	<Grid>
		<ReturnButton text="Home"/>
		<PostName text={postName}/>
		<Tags data={tags}/>

		<!-- <PostName text={postName}></PostName>
		<p style="grid-area: block;"></p>
		-->
		
		<h1 style="grid-area: title;">Page TitleVestibulum ante ipsum primis in faucibus orci luctus et ultrices.</h1>
		<div style="grid-area: content;">
			<p>Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Donec velit neque, auctor sit amet aliquam vel, ullamcorper sit amet ligula. Nulla quis lorem ut libero malesuada feugiat. Nulla porttitor accumsan tincidunt. Curabitur non nulla sit amet nisl tempus convallis quis ac lectus.</p>
			<ul class="">
				<li>test1</li>
				<li>test2</li>
				<li>test3</li>
			</ul>
			<ol>
				<li>test1</li>
				<li>test2</li>
				<li>test3</li>
			</ol>
		</div>
	</Grid>
</main>

<style lang="scss">
  	@import "./static/core/global";
	@import "./static/core/atoms";
	
</style>
