<script lang="ts">
    import Tags from "../molecules/tags.molecule.svelte";
	import PostName from "../molecules/post-name.molecule.svelte";
	import ReturnButton from "../molecules/button.molecule.svelte";
    import type { Tag } from "../molecules/tags.molecule.svelte";

    
    export let label: string;
    export let tags: Tag[];

</script>

<ReturnButton href="/" text="Home"/>
<PostName text={label}/>
<Tags data={tags}/>