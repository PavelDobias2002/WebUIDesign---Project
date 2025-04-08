<script>
    import { onMount } from 'svelte';
    import { scale } from 'svelte/transition';
    import ArticleCard from '$lib/components/ArticleCard.svelte';
    
    onMount(() => {
        console.log("about page loaded");
    });

    // import base to prefix local paths
    import { base } from '$app/paths';

    // Article data
    const articles = [
        {
            title: "Return to Hyrule!",
            description: "Watch Link adventure to theatres on March 26th 2027!",
            image: "{base}zelda.jpg",
            link: "{base}/articleFallout"
        },
        {
            title: "Tron:Ares and it's Soundtrack",
            description: "Could Tron:Ares revive the legendary music duo Daft Punk?",
            image: "{base}daft-punk.jpg",
            link: "{base}/articleFallout"
        },
        {
            title: "Live-action or Animated?",
            description: "Fans are spilt between Mojang's decision for a live-action Minecraft movie.",
            image: "{base}mc-movie.png",
            link: "{base}/articleFallout"
        },
        {
            title: "Roll-Out to the Fallout!",
            description: "Amazon Prime's Fallout is gearing up for it's 2nd Season!",
            image: "{base}fallout.jpg",
            link: "{base}/articleFallout"
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
        padding-top: 5%;
        text-align: center;
        color: var(--articles-color);
        font-size: 120px;
        margin-bottom: 2rem;
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
        border-bottom: 4px solid var(--articles-color);
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
            transform: translateY(50px);
        }
        100% {
            opacity: 1;
            transform: translateY(0);
        }
    }
</style>