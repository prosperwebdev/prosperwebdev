<script lang="ts">
    import type {HTMLAttributes} from 'svelte/elements';
    import SearchIcon from '$lib/icons/search.svelte';

    interface Props extends HTMLAttributes<HTMLDivElement> {        
    }

    let {class:className, ...divProps}: Props = $props();
</script>

<div class="search {className}" {...divProps}>
    <SearchIcon />
</div>

<style>
    .search {
        --icon-color: var(--grayscale-900);

        background-color: var(--content-line-color);
        box-shadow: var(--content-shadow);
    
        border-radius: var(--radius-round);
    
        padding: var(--size-1);
        height: var(--size-5);
    }
</style>