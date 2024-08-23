<script lang="ts">
    import FauxThumbImage from './faux-thumb-image.svelte';
    import FauxContent from './faux-content.svelte';
    import type {HTMLAttributes} from 'svelte/elements';

    interface Props extends HTMLAttributes<HTMLDivElement> {
        lines?: string[];    
    }

    let {lines, class:className, ...divProps}: Props = $props();
</script>

<div class="thumb {className}" {...divProps}>
    <FauxThumbImage class="faux-thumb" />
    <FauxContent class="faux-thumb-content" {lines} />
</div>

<style>
    .thumb {    
        grid-column: 1 / -1;
        display: grid;
        grid-template-columns: subgrid; 
        
    }
</style>

