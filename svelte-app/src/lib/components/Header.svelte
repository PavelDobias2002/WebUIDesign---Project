<script>
    import { Navigation} from "$lib"
</script>
<header>
    <header>
        <div class="TV-logo">
        <img src="/logo.png" alt="Website Logo">
        </div>
</header>
<Navigation />
</header>


<style>
    /* Header Styling */
    header {
        display: flex;
        align-items: center;
        justify-content: space-between;
        background-color: var(--primary-color);
        color: white;
        padding: 1rem;
    }

    /* Logo Container */
    .TV-logo {
        display: flex;
        align-items: center;
    }

    .TV-logo imga{
        width: 50px;
        margin-right: 0.625rem;
    }
</style>