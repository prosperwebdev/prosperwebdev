<script lang="ts">
    import Header from '$lib/header.svelte';
    import Footer from '$lib/footer.svelte';
    import "../style.css";
    let {children} = $props();
</script>

<Header />
<main>
    {@render children()}
</main>
<Footer />

<style>
    :global(body) {
        display: flex;
        flex-flow: column nowrap;
    }

    main {
        flex: 1 1 auto;
    }
</style>