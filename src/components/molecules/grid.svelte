
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
        grid-auto-columns: minmax(min-content, 1fr);
        column-gap: var(--row-gap);
        row-gap: var(--col-gap);
        position: relative;
    }

    @media only screen and (max-width: 800px) {
        .grid {
            grid-template-areas: 
                "back           name        tags        tags        "
                "title          title       title       title       "
                "content        content     content     content     ";
        }
    }
</style>