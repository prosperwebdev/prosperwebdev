<script lang="ts">
    import type {Snippet} from 'svelte';
    import type {HTMLAttributes} from 'svelte/elements';
    import FauxSearch from './faux-search.svelte';
    import FauxContent from './faux-content.svelte';
    import FauxImage from './faux-image.svelte';
    import FauxAside from './faux-aside.svelte';

    interface Props extends HTMLAttributes<HTMLDivElement> {
        children?: Snippet<[]>;
    }

    let {children, class:className, ...divAttrs}: Props = $props();
</script>

<div class="app {className}" {...divAttrs}>
    <FauxSearch class="faux-search" />
    <FauxImage class="faux-image" content={children}/>
    <FauxContent class="faux-content-main" lines={['60%', '85%', '45%', '75%']} />
    <FauxAside class="faux-aside" />
</div>

<style>
    .app {
        container-type: inline-size;
        container-name: fauxapp;

        inline-size: 100%;

        --content-line-color: var(--grayscale-200);
        --shadow-strength: 50%;
        --shadow: 
            3px 3px 5px -2px hsl(var(--shadow-color) / calc(var(--shadow-strength) + 3%)),
            7px 7px 14px -5px hsl(var(--shadow-color) / calc(var(--shadow-strength) + 5%));
        --content-shadow: var(--shadow);
        /* --content-shadow: 3px 3px 4px rgba(0, 0, 0, 0.65); */
        --icon-drop-shadow: 1px 1px 0.75px rgba(0, 0, 0, 0.8);

        aspect-ratio: 4 / 3;

        background-color: var(--grayscale-700);
        box-shadow: var(--shadow-2);

        border-radius: var(--radius-3);
        padding: var(--size-5);

        position: relative;
        display: grid;
        grid-template-columns: [search-start image-start content-start] 3fr [content-end image-end aside-start] 2fr [aside-end search-end];
        grid-template-rows: [search-start] auto [search-end image-start aside-start] 3fr [image-end content-start] 1fr [content-end aside-end];   
        gap: var(--size-5);     
    }

    :global(.app > .faux-content-main) {
        grid-column: content;
        grid-row: content;        
    }

    :globa(.app > .faux-image) {
        grid-column: image;
        grid-row: image;
    }

    :global(.app > .faux-search) {
        grid-column: search;
        grid-row: search;
        min-inline-size: 70%;
        justify-self: center;
    }

    :global(.app > .faux-aside) {
        grid-column: aside;
        grid-row: aside;
    }
</style>