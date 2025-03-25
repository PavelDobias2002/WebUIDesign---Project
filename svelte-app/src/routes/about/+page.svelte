<script>
    import { onMount } from 'svelte';
    
    onMount(() => {
        console.log("about page loaded");
    });
</script>

<div class="bg"></div>
<div class="content">
    <h1 class="reveal-text">About...</h1>
    <img src="/logo.png" alt="NoSignalMedia" class="reveal-logo">
</div>

<style>
    h1{
        color: white;
    }
    
    /* Second background (add your preferred background or use the same as home) */
    .bg {
        position: fixed; /* Fixed position for the background */
        width: 100%;
        height: 100vh;
        z-index: 0;
        top: 0;
        left: 0;
        background-size: cover;
        background-position: center;
        animation: gifs 15s infinite steps(1);
        overflow: hidden;
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

    @keyframes gifs {
        0%, 12% { 
            background-image: url('/dexter-show.gif');
        }

        13%, 20% { 
            background-image: url('/minecraft.gif');
        }
        21%, 30% { 
            background-image: url('/the-batman.gif');
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
