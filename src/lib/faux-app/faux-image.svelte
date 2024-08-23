<script lang="ts" generics="T">
    import type {Snippet} from 'svelte';
    import type {HTMLAttributes} from 'svelte/elements';

    interface Props extends HTMLAttributes<HTMLDivElement> {        
        content?: Snippet<[]>;
    }

    let {content, class:className, ...divProps}: Props = $props();
</script>

<div class="image {className}" {...divProps}>
    {#if content}
        {@render content()}
    {/if}
</div>

<style>
    .image {
        min-width: 100%;
        min-height: 100%;

        padding: var(--size-3);
        overflow: hidden;

        background-color: var(--image-background-color, var(--grayscale-100));
        box-shadow: var(--content-shadow);

        border-radius: var(--radius-3);
    }

</style>