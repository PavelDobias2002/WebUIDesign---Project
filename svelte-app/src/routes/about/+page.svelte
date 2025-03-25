<script>
    import { onMount } from 'svelte';
    
    onMount(() => {
        console.log("about page loaded");
    });
</script>

<div class="overlay"></div>
<div class="content">
    <h1 class="reveal-text">About...</h1>
    <img src="/logo.png" alt="NoSignalMedia" class="reveal-logo">
</div>
<div class="image-container">
    <img src="/jake-kelly.png" alt="no.1" class="flex-image">
    <img src="/pavel.png" alt="no.2" class="flex-image">
    <img src="/eliska.png" alt="no.3" class="flex-image">
</div>

<style>
    h1{
        color: white ;
    }
    .overlay {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: linear-gradient(to bottom, 
            rgba(0,0,0,0.2) 0%,
            rgba(0,0,0,0.4) 60%, 
            rgba(0,0,0,0.7) 100%);
        z-index: -1;
    }

    .reveal-logo {
        display: flexbox;
        opacity: 0;
        transform: translateY(20px);
        animation: revealLogo 1.2s forwards ease-out;
        animation-delay: 0.1s;
        max-width: 25%;
        height: auto;
        margin: 0px auto 10px;
    }

    .image-container {
        display: flex;
        justify-content: space-between;
        align-items: center;
        gap: 20px;
        margin: 40px auto;
        max-width: 1200px;
        padding: 0 20px;
        flex-wrap: wrap;
    }
    
    .flex-image {
        width: 100%;
        max-width: 300px;
        height: auto;
        border-radius: 8px;
        opacity: 0;
        transform: translateY(20px);
        animation: revealLogo 1.2s forwards ease-out;
        animation-delay: 0.3s;
        transition: transform 0.3s ease;
    }

    .reveal-text {
        opacity: 0;
        transform: translateY(20px);
        animation: revealText 1s forwards ease-out;
    }
    
    .content h1 {
        font-size: 120px;
        text-shadow: 0 0 15px rgba(255, 255, 255, 0.3);
        transition: text-shadow 0.3s ease, transform 0.3s ease;
        animation-delay: 0.2s;
    }

    .content h1:hover {
        text-shadow: 0 0 25px rgba(255, 255, 255, 0.5);
        transform: scale(1.02)
    }

    @keyframes revealText {
        0% {
            opacity: 0;
            transform: translateY(100px);
        }
        100% {
            opacity: 1;
            transform: translateY(0);
        }
    }

    @keyframes revealLogo {
        0% {
            opacity: 0;
            transform: translateY(100px);
        }
        100% {
            opacity: 1;
            transform: translateY(0);
        }
    }
</style>
