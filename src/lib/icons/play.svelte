<script lang="ts">
    import type { SVGAttributes } from 'svelte/elements';
    
    let { ...svgProps }: SVGAttributes<SVGElement> = $props();
</script>

<svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" {...svgProps}>
    <circle cx="12" cy="12" r="10"/>
    <path d="M15.4137 10.941C16.1954 11.4026 16.1954 12.5974 15.4137 13.059L10.6935 15.8458C9.93371 16.2944 9 15.7105 9 14.7868L9 9.21316C9 8.28947 9.93371 7.70561 10.6935 8.15419L15.4137 10.941Z"/>
</svg>

<style>
    svg {
        height: var(--icon-height, 100%);
        fill: var(--icon-background-color, none);        
    }

    circle, path {
        stroke: var(--icon-color, var(--grayscale-200));
        stroke-width: var(--icon-stroke-size, 1);
        filter: drop-shadow(var(--icon-drop-shadow));        
    }
</style>