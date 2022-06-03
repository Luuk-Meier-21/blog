<script lang="ts">
    import Tags from "../molecules/tags.svelte";
	import PostName from "../molecules/post-name.svelte";
	import ReturnButton from "../molecules/return-button.svelte";
    import type { Tag } from "../molecules/tags.svelte";

    
    export let postName: string;
    export let tags: Tag[];

</script>

<ReturnButton href="/" text="Home"/>
<PostName text={postName}/>
<Tags data={tags}/>