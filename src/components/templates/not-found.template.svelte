<script lang="ts">
    import HomeButton from "../molecules/home-button.molecule.svelte";

    export let message: string = "Oops page not found...";
</script>

<h1 class="status-title is--accent">404</h1>
<article class="status-content">
    <p>{message}</p>
    <HomeButton text="Go back home" href="/"/>
</article>