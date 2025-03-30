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

<div class="about-section">
    <p class= "reveal-text">Kingdom Come: Deliverance 2 stands as the greatest game of all time because it masterfully blends historical authenticity, deep role-playing mechanics, and immersive storytelling. Unlike other RPGs that rely on fantasy elements, KCD2 grounds itself in a meticulously researched medieval world, where every detail—from the architecture to the clothing and even the way people speak—feels true to its time period. The combat system is one of the most realistic in gaming, demanding skill, patience, and strategy rather than simple button-mashing. Meanwhile, the game world is alive, with NPCs following their own routines, reacting to your choices, and making every playthrough feel unique. This level of realism and dedication to historical accuracy sets it apart from anything else in the genre.

        Beyond its technical achievements, KCD2 excels in delivering a deeply personal and rewarding player experience. The freedom it offers allows you to shape your character’s journey, choosing between diplomacy, combat, or cunning to overcome obstacles. The progression system is both realistic and satisfying, ensuring that every skill you develop feels earned rather than handed to you. Its open world is not just vast but meaningful, filled with rich side quests that rival the depth of the main story. The emotional weight of the narrative, combined with stunning visuals and a beautifully composed soundtrack, makes for an unforgettable experience. By prioritizing realism, player agency, and storytelling in ways few games dare to, KCD2 solidifies itself as the pinnacle of immersive gaming.</p>
</div>

<div class="image-container">
    <img src="/jake-kelly.png" alt="Jake Kelly" class="flex-image">
    <img src="/eliska.png" alt="Eliska Vrzalova" class="flex-image">
    <img src="/pavel.png" alt="Pavel Dobias" class="flex-image">
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
        max-width: 500px;
        height: auto;
        margin: 0px auto 10px;
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
        line-height: 1.6;
        text-align: justify;
        animation-delay: 0.5s;
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
