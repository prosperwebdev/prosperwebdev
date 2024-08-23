<script lang="ts">
    import type {HTMLAttributes} from 'svelte/elements';

    interface Props extends HTMLAttributes<HTMLDivElement> {    
        lines?: string[];    
    }

    let {lines=['50%', '75%', '35%', '65%'], class:className, ...divProps}: Props = $props();
</script>

<div class="content {className}" {...divProps}>
    {#each lines as width}
        <div class="line" style="--width:{width};"></div>
    {/each}
</div>

<style>
    .content {
        min-inline-size: 100%;
        min-block-size: 100%;

        display: flex;
        flex-flow: column nowrap;
        gap: var(--content-line-gap, var(--size-3));

        padding-block: var(--content-padding-block, 0);
    }

    .line {
        background-color: var(--content-line-color);
        box-shadow: var(--content-shadow);

        border-radius: var(--radius-round);
        inline-size: var(--width);

        block-size: var(--content-line-height, var(--size-3));
    }
</style>