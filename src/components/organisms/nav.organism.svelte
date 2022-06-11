<script lang="ts">
    import Tags from "../molecules/tags.molecule.svelte";
	import PostName from "../molecules/post-name.molecule.svelte";
	import ReturnButton from "../molecules/home-button.molecule.svelte";
    import type { Tag } from "../molecules/tags.molecule.svelte";
    import { Route } from "svelte-routing";
    
    export let label: string;
    export let tags: Tag[] = undefined;
    export let tagLabel: string = undefined;

    let isHome = window.location.pathname === "/";
    console.log(isHome)
</script>

{#if !isHome}   
    <ReturnButton href="/" text="Home"/> 
{/if}
<p class="nav-label">
    {@html label}
</p>
{#if tags} 
    <div class="nav-tags">
        {#if tagLabel} 
            <p>{tagLabel}</p>
        {/if}
        <Tags data={tags}/>
    </div> 
{/if}

<style lang="scss">
    .nav-label {
        grid-area: label;
    }   

    .nav-tags {
        grid-area: tags;

        p {
            margin: 0;
            display: inline;
        }
    }
</style>