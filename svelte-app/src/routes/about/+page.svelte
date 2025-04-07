<script>
    import { onMount } from 'svelte';
    
    onMount(() => {
        console.log("about page loaded");
    });
</script>

<div class="overlay"></div>

<div class="content">
    <h1 class="reveal-text">About Us</h1>
</div>

<div class="about-section">
    <p class= "reveal-text">No Signal Media was born from our deep love of movies and the excitement of building something meaningful from the ground up. Film has always been more than just entertainment for us. It is an art form that tells stories, evokes emotions, and sparks conversations. Whether it is analyzing the intricate details of a classic masterpiece, diving into the latest releases, or exploring the evolving landscape of cinema, we are passionate about breaking down what makes movies so powerful. We want to create a space where film lovers can come together to celebrate the magic of storytelling, share unique perspectives, and engage in thoughtful discussions about the art of filmmaking. Just as much as we enjoy writing about and discussing films, we love shaping No Signal Media itself. Every update, every design tweak, and every new feature is an extension of our passion for both cinema and digital creation. Building this platform is a creative process in its own right, and we take pride in crafting a space that truly reflects our enthusiasm. As the site grows, so does our excitement for what is ahead. New ideas, deeper conversations, and a community of like-minded movie lovers who share in our appreciation. For us, No Signal Media is more than just a website. It is a labor of love, a creative outlet, and a constantly evolving home for film enthusiasts who, like us, believe that movies are worth celebrating.</p>
</div>

<div class="image-container">
    <img src="/jake-kelly.png" alt="Jake Kelly" class="flex-image">
    <img src="/eliska.png" alt="Eliska Vrzalova" class="flex-image">
    <img src="/pavel.png" alt="Pavel Dobias" class="flex-image">
</div>


<style>
    h1{
        padding-top: 4rem;
        color: var(--about-color);
        border-bottom: 10px solid var(--about-color);
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


    .image-container {
        display: flex;
        justify-content: space-between;
        align-items: center;
        gap: 20px;
        margin: 120px auto;
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

    .about-section {
        max-width: 1500px;
        margin: 60px auto;
        padding: 0 20px;
        text-align: center;
    }

    .about-section p {
        color: white;
        font-size: 25px;
        font-family: "Exo 2", sans-serif;
        line-height: 1.6;
        text-align: justify;
        animation-delay: 0.5s;
    }

    .reveal-text {
        opacity: 0;
        transform: translateY(20px);
        animation: revealText 1s forwards ease-out;
    }
        
    @keyframes revealText {
        0% {
            opacity: 0;
            transform: translateY(50px);
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
