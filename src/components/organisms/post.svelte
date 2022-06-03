<script lang="ts">
    export let title: string;
    export let content: string;
</script>

<h1 class="title">{title}</h1>
<p class="content">{@html content}</p>

<style lang="scss">
    .title {
        grid-area: title;
    }

    .content {
        grid-area: content;
    }
</style>
