<script>
    import Header from "../components/header.svelte";
    import Hero from "../components/hero.svelte";
    import Test from "../components/test.svelte";

    import { onMount } from "svelte";

    // set the page title in the browser
    onMount(() => {
        document.title = "Home | SvelteKit";
    });

</script>

<div class="container p-0" style="overflow: hidden;">
    <Header />
    <Hero/>
</div>
