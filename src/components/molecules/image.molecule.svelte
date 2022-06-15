<script lang="ts" context="module">
    export interface ImageData {
        img: {
            url: string;
        }
        alt: string;
        caption: string;
    }
</script>


<script lang="ts">
    export let src: string;
    export let alt: string;
    export let caption: string;
</script>

<figure class="image">
    <img class="image__source" src={src} alt={alt}>
    <figcaption class="image__caption is--small">{caption}</figcaption>
</figure>

<style lang="scss">
    .image {
        width: 100%;

        &__source {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        &__caption {
            
        }
    }
</style>