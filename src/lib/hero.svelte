<script lang="ts">
    import FauxApp from '$lib/faux-app/faux-app.svelte';
</script>

<section class="hero full-width">
    <div class="hero__layout">        
        <FauxApp class="faux-app">
            <div class="call-to-action">
                <hgroup class="hook">
                    <h2>Building user delight in every application</h2>
                    <p>Contact us for a free consultation</p>
                </hgroup>
                <form class="email-form">
                    <label for="email-input" class="email-label">Email</label>
                    <input id="email-input" placeholder="dreambig@email.com" type="email" />
                    <button class="email-submit">Contact Us</button>
                </form>
            </div>
        </FauxApp>        
    </div>
</section>

<style>
    .hero {
        --image-background-color: var(--primary-800);

        background-color: var(--clr-primary);
        color: var(--clr-text);

        padding-block: var(--size-7);
    }

    .hero__layout {      
        grid-column: breakout;     
    }

    .call-to-action {
        block-size: 100%;
        inline-size: 100%;

        position: relative;
    }

    .email-form {
        position: absolute;
        bottom: 0;
        left: 0;
        right: 0;

        display: grid;
        grid-template-columns: [input-start] 1fr [input-end button-start] auto [button-end];
        grid-auto-rows: auto;
        column-gap: var(--size-2);
    }

    .email-label {
        display: block;
        grid-column: 1 / -1;
    }

    #email-input {
        grid-column: input;
    }

    .email-submit {
        grid-column: button;
    }

    .hook h2 {
        font-size: var(--font-size-5);
        line-height: var(--line-height-5);
    }
</style>