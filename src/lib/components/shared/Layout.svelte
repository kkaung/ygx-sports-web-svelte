<script>
    import BottomTabs from './BottomTabs.svelte';
    import Footer from './Footer.svelte';
    import Navbar from './Navbar.svelte';
    import SponseredBrandsMarquee from './SponseredBrandsMarquee.svelte';
</script>

<div class="main">
    <Navbar />
    <main>
        <slot />
        <!-- <SponseredBrandsMarquee /> -->
    </main>
    <BottomTabs />
    <Footer />
</div>

<style>
    .main {
    }

    main {
        min-height: calc(100vh - 62px - 49px - 100px);
    }
</style>
