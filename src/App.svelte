
<script lang="ts">
	import Grid from "./components/molecules/grid.molecule.svelte";
	import PostTemplate from "./components/templates/post.template.svelte"
	import Loader from "./components/organisms/loader.organism.svelte"
	import Home from "./components/templates/home.template.svelte";
	import { Router, Route, Link } from "svelte-routing";
	
	export let url = "";
</script>

<div>
	<Router url={url}>
		<Grid>
			<Loader>
				<Route path="/"><Home/></Route> 
				<Route path="posts/:postSlug" component={PostTemplate}></Route>
			</Loader>
		</Grid>
	</Router>
</div>

<style lang="scss">
  	@import "./static/core/global";
	@import "./static/protons";
	@import "./static/atoms";
</style>
