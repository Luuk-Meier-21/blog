
<main class="grid">
    <slot></slot>
</main>

<style lang="scss">
    .grid {
        display: grid;
        grid-template-areas: 
            "back   name        tags        ."
            ".      title       title       ."
            ".      content     content     .";
        grid-auto-rows: minmax(var(--row-height), auto);  
        grid-auto-columns: 1fr;
        column-gap: var(--row-gap);
        row-gap: var(--col-gap);
        position: relative;
    }
</style>