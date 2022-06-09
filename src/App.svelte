
<script lang="ts">
	import Grid from "./components/molecules/grid.molecule.svelte";
	import PostTemplate from "./components/templates/post.template.svelte";
	import Loader, { ApiRef } from "./components/organisms/loader.organism.svelte";
	import Home from "./components/templates/home.template.svelte";
	import { Router, Route, Link } from "svelte-routing";
	import NotFound from "./components/templates/not-found.template.svelte";
	import FilterTemplate from "./components/templates/filter.template.svelte";

	export let url = "";
</script>

<div>
	<Router url={url}>
		<Grid>
			<Loader>
				<Route path="/"><Home/></Route>
				<Route path="posts/:postSlug" component={PostTemplate}></Route>
				<Route path="filter/:tagSlug" component={FilterTemplate}></Route>
				<Route path="*"><NotFound/></Route>
			</Loader>
		</Grid>
	</Router>
</div>

<style lang="scss">
  	@import "./static/core/global";
	@import "./static/protons";
	@import "./static/atoms";
</style>
