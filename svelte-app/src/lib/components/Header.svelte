<script>
    // import Navigation.svelte from lib folder
    import { Navigation } from "$lib"
</script>


<header>
    <!-- Navigation -->
    <Navigation />
</header>


<style>
    /* Header Styling */
    header {
        display: flex;
        align-items: center;
        color: white;
        padding: 1rem;
    }


    /* Mobile: Center logo and stack items */
    @media (max-width: 768px) {
        header {
        
            text-align: center;

        }

    }
</style>