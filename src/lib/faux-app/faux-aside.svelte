<script lang="ts">
    import type {HTMLAttributes} from 'svelte/elements';
    import FauxThumb from './faux-thumb.svelte';

    interface Props extends HTMLAttributes<HTMLDivElement> {        
    }

    let {class:className, ...divProps}: Props = $props();

    const lines = ['75%', '100%', '60%', '90%'];
</script>

<div class="aside {className}" {...divProps}>
    <FauxThumb {lines} class="faux-thumb" />
    <FauxThumb {lines} class="faux-thumb" />
    <FauxThumb {lines} class="faux-thumb" />
    <FauxThumb {lines} class="faux-thumb" />
    <FauxThumb {lines} class="faux-thumb" />
</div>

<style>
    .aside {       
        --content-line-height: var(--size-2);
        --content-line-gap: var(--size-2);
        --content-padding-block: var(--size-2);
        --icon-color: var(--grayscale-100);

        --thumb-background-color: var(--clr-accent);
        
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-auto-rows: min-content;
        column-gap: var(--size-3);
        row-gap: var(--size-5);
    }    
</style>