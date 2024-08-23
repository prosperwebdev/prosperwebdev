<script lang="ts">
    import type {HTMLAttributes} from 'svelte/elements';
    import Play from '$lib/icons/play.svelte';

    interface Props extends HTMLAttributes<HTMLDivElement> {  
    }

    let {class:className, ...divProps}: Props = $props();
</script>

<div class="thumb-image {className}" {...divProps}>
    <Play/>
</div>

<style>
    .thumb-image {
        min-width: 100%;
        aspect-ratio: 16 / 9;

        background-color: var(--thumb-background-color);
        box-shadow: var(--content-shadow);

        border-radius: var(--radius-2);
        padding: var(--size-2);

        display: grid;
        place-items: center;
    }
</style>