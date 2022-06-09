<script lang="ts">
    import Loader from "../organisms/loader.organism.svelte";
    import type { ApiRef, ApiData } from "../organisms/loader.organism.svelte";
    import Nav from "../organisms/nav.organism.svelte";
    import Posts from "../organisms/posts.organism.svelte";
    import type { Tag } from "../molecules/tags.molecule.svelte";
    import type { PostData } from "../organisms/post.organism.svelte";
    import { getContext } from "svelte";

    const {tags, blogPosts} = getContext<ApiData>("api");
</script>

<Nav label="Luuk Meier" tagLabel="Filter: " tags={tags}/>
<Posts posts={blogPosts}/>


<style lang="scss">
    .home {
        grid-area: title;
    }
</style>
