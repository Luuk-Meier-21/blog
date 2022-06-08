<script lang="ts">
    import Tags from "../molecules/tags.molecule.svelte";
	import PostName from "../molecules/post-name.molecule.svelte";
	import ReturnButton from "../molecules/home-button.molecule.svelte";
    import type { Tag } from "../molecules/tags.molecule.svelte";

    
    export let label: string;
    export let tags: Tag[] = undefined;

    let isHome = window.location.pathname === "/";
    console.log(isHome)
</script>

{#if !isHome}   <ReturnButton href="/" text="Home"/> {/if}
<PostName text={label}/>
{#if tags}      <Tags data={tags}/>     {/if}