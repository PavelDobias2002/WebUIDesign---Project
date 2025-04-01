<script>
    import { onMount } from 'svelte';
    import { scale } from 'svelte/transition';
    import ArticleCard from '$lib/components/ArticleCard.svelte';
    
    onMount(() => {
        console.log("about page loaded");
    });

    // Article data
    const articles = [
        {
            title: "Return to Hyrule!",
            description: "Watch Link adventure to theatres on March 26th 2027!",
            image: "zelda.jpg",
            link: "/articleFallout"
        },
        {
            title: "Tron:Ares and it's Soundtrack",
            description: "Could Tron:Ares revive the legendary music duo Daft Punk?",
            image: "daft-punk.jpg",
            link: "/articleFallout"
        },
        {
            title: "Live-action or Animated?",
            description: "Fans are spilt between Mojang's decision for a live-action Minecraft movie.",
            image: "mc-movie.png",
            link: "/articleFallout"
        },
        {
            title: "Roll-Out to the Fallout!",
            description: "Amazon Prime's Fallout is gearing up for it's 2nd Season!",
            image: "fallout.jpg",
            link: "/articleFallout"
        }
    ];
</script>

<div class= "overlay"></div>

<h1 class="reveal-text">Latest Articles</h1>

<div class="article-grid">
    {#each articles as article}
        <ArticleCard 
            title={article.title}
            description={article.description}
            image={article.image}
            link={article.link}
        />
    {/each}
</div>

<style>
    h1 {
        text-align: center;
        color: white;
        font-size: 120px;
        text-shadow: 0 0 15px rgba(255, 255, 255, 0.3);
        transition: text-shadow 0.3s ease, transform 0.3s ease;
    }
    
    h1:hover {
        text-shadow: 0 0 25px rgba(255, 255, 255, 0.5);
        transform: scale(1.02)
    }

    .article-grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(400px, 1fr));
        gap: 2rem;
        max-width: 1200px;
        position: relative;
        margin: 0 auto;
    }
    
    .reveal-text {
        opacity: 0;
        transform: translateY(20px);
        animation: revealText 1s forwards ease-out;
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
    
    @keyframes revealText {
        0% {
            opacity: 0;
            transform: translateY(20px);
        }
        100% {
            opacity: 1;
            transform: translateY(0);
        }
    }
</style>