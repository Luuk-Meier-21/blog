<script lang="ts">
    import { getContext } from "svelte";
    import PostLink from "../molecules/post-link.molecule.svelte";
    import Nav from "../organisms/nav.organism.svelte";
    import type { PostData } from "../organisms/post.organism.svelte";
    import Posts from "../organisms/posts.organism.svelte";
</script>


<Nav label="Luuk Meier" tagLabel="Filter: " tags={post}/>
<Posts posts={posts}/>

<style>
    .home {
        grid-area: title;
    }
</style>
