<script lang="ts">
	import Grid from "./components/molecules/grid.svelte";
	import type { Tag } from "./components/molecules/tags.svelte";
import Nav from "./components/organisms/nav.svelte";
import Post from "./components/organisms/post.svelte";
	
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
	const content = "<p>Quisque velit nisi, pretium ut <a>lacinia</a> in, elementum id enim. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur aliquet quam id dui posuere blandit.</p>";
	const title = "Tijdens mijn oude web develoment stage bij Foster vond ik het altijd erg fijn dat ik alles waar ik tegenaan liep meteen kon vragen. Het direct oplossen van mijn probleem leek mij erg handig en juist efficent. ";

</script>

<main>
	<Grid>
		<Nav postName="test" tags={tags}/>
		<Post title={title} content={content}></Post>
	</Grid>
</main>

<style lang="scss">
  	@import "./static/core/global";
	@import "./static/core/atoms";
	
</style>
