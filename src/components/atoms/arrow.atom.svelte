<script lang="ts">
    type IconWeight = "regular" | "bold"
    type IconDirection = "left" | "right"
    export let weight: IconWeight = "regular";
    export let direction: IconDirection = "left";

    let strokeWidth = weight === "bold" ? "is--bold" : "is--regular";
    let iconDirection = direction === "right" ? "is--right" : "is--left";
    let classes = `arrow ${iconDirection} ${strokeWidth}`;
</script>

<figure class={classes}>
    <svg class="arrow__icon" viewBox="0 0 12 12" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M6.36642 0.577392L1 5.94382L6.36642 11.3102" stroke="inherit"/>
        <path d="M1.30701 5.94382L11.426 5.94382" stroke="inherit"/>
    </svg>
</figure>
    
<style lang="scss">
    .arrow {
        stroke: inherit;
        display: inline-block;
        margin: 0;
        width: auto;

        &__icon {
            display: inline-flex;
            height: .75em;
            // transform: translateY(.05em);
            vertical-align: baseline;
            width: auto;
        }
        
        &.is--left { 
            margin-right: .5rem;
        };

        &.is--right { 
            transform: rotate(180deg);
            margin-left: .5rem;
        };

        &.is--bold { 
            stroke-width: 1.5px
        };
    }
</style>