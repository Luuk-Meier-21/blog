<script lang="ts">
    import { getContext } from "svelte";
    import PostLink from "../molecules/post-link.molecule.svelte";
import Nav from "../organisms/nav.organism.svelte";
    import type { PostData } from "../organisms/post.organism.svelte";
    import PostsTemplate from "../organisms/posts.organism.svelte";
    

    const posts: PostData[] = getContext('posts');
</script>

<Nav label="Luuk Meier"/>
<PostsTemplate posts={posts}/>

<style>
    .home {
        grid-area: title;
    }
</style>
