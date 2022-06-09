<script lang="ts">
    import Loader from "../organisms/loader.organism.svelte";
    import type { ApiRef } from "../organisms/loader.organism.svelte";
    import Nav from "../organisms/nav.organism.svelte";
    import Posts from "../organisms/posts.organism.svelte";
    import type { Tag } from "../molecules/tags.molecule.svelte";
    import type { PostData } from "../organisms/post.organism.svelte";

    interface HomeData {
        tags?: Tag[];
        blogPosts?: PostData[];
    }

    const homeRef: ApiRef = {
        url: "https://api-eu-west-2.graphcms.com/v2/cl3ossjir6ju301z6grqwfdf9/master?query=query%20MyQuery%20%7B%0A%20%20tags%20%7B%0A%20%20%20%20label%0A%20%20%20%20url%0A%20%20%7D%0A%20%20blogPosts%20%7B%0A%20%20%20%20slug%0A%20%20%20%20title%0A%20%20%20%20tags%20%7B%0A%20%20%20%20%20%20label%0A%20%20%20%20%20%20url%0A%20%20%20%20%7D%0A%20%20%20%20content%20%7B%0A%20%20%20%20%20%20html%0A%20%20%20%20%20%20text%0A%20%20%20%20%7D%0A%20%20%7D%0A%7D&operationName=MyQuery",
        queryName: ""
    }

    let data: HomeData = {};
</script>

<Loader ref={homeRef} bind:data={data}>
    <Nav label="Luuk Meier" tagLabel="Filter: " tags={data.tags}/>
    <Posts posts={data.blogPosts}/>
</Loader>


<style>
    .home {
        grid-area: title;
    }
</style>
