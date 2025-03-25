<script>
    import { onMount } from 'svelte';
    import { Card } from '$lib';
    import { Card2 } from '$lib';
    
    let cardContainer;
    let cards = [];

    let movieContainer;
    let movies = [];
    onMount(() => {
        console.log("home page loaded");
        
        // Set up Intersection Observer for parallax scroll effect
        if (typeof IntersectionObserver !== 'undefined') {   //intersectionobserver - watches visibility of elements
            const cardOptions = {
                root: null,
                rootMargin: '-100px 0px', // observer is triggered when above or bellow 100px
                threshold: [0, 0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9, 1] //percentages of visibility when the observer is triggered
            };
             const movieOptions = {
                root: null,
                rootMargin: '-100px 0px',
                threshold: [0, 0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9, 1]
            };

        
            
            // Observer for cards with enhanced animations
            const cardObserver = new IntersectionObserver((entries) => {
                entries.forEach(entry => {  // what is visible
                    if (entry.isIntersecting) {
                        const ratio = Math.min(entry.intersectionRatio * 1.5, 1); // intersection ratio- how much of the element needs to be visible
                        const index = Array.from(cards).indexOf(entry.target);
                        // Add staggered delay for cards
                        const delay = index * 0.1;
                        entry.target.style.transitionDelay = `${delay}s`; //staggered animation
                        entry.target.style.opacity = ratio;
                        entry.target.style.transform = `translateY(${(1 - ratio) * 70}px) scale(${0.8 + ratio * 0.2})`; // card moves up and scales up
                    }
                });
            }, cardOptions);

            const movieObserver = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if(entry.isIntersecting)
                {
                    const ratio = Math.min(entry.intersectionRatio * 1.5, 1) ; // visibility calculation, makes the effect stroger by multiplying the visibility but its capped at 1 so it never exceeds it
                    const index = Array.from(movies).indexOf(entry.target); // finding index of current movie card
                    const delay = index * 0.1;
                    entry.target.style.transitionDelay = `${delay}s`; //staggered animation
                    entry.target.style.opacity = ratio;
                    entry.target.style.transform =  `translateY(${(1 - ratio) * 70}px) scale(${0.8 + ratio * 0.2})`;
                }
                })
            }, movieOptions);
            
            
            // Track scroll position for parallax effects
            window.addEventListener('scroll', () => {
                const scrollY = window.scrollY;
                const parallaxContainer = document.querySelector('.parallax-container');
                const content = document.querySelector('.content');
                const parallaxContainer2 = document.querySelector('.parallax-container2');
                const content2 = document.querySelector('.content2');
                
                if (parallaxContainer) {
                    // Calculate the transform based on scroll position
                    const translateY = Math.min(scrollY * 0.05, 50); // slowed down when i scroll until i reach 50px
                    parallaxContainer.style.transform = `translateY(${translateY}px)`;
                    parallaxContainer2.style.transform = `translateY(${translateY}px)`;
                }
                
                if (content) {
                    // Adjust content position and opacity based on scroll
                    if (scrollY > 50) {
                        content.style.transform = `translateY(${scrollY * 0.03}px)`; // slower when i scroll past 50px (every 10px it moves down by 3px)
                        content.style.opacity = Math.max(1 - scrollY / 500, 0.1); /* Fade out a bit faster, opacity increases as i scroll, but is at least 0.1 */
                        content2.style.transform = `translateY(${scrollY * 0.03}px)`; // slower when i scroll past 50px
                        content2.style.opacity = Math.max(1 - scrollY / 500, 0.1); /* Fade out a bit faster */
                    } else {
                        //initial state
                        content.style.transform = 'translateY(0)'; //when the scroll pos is very low it doesnt fade or move
                        content.style.opacity = 1;
                        content2.style.transform = 'translateY(0)';
                        content2.style.opacity = 1;
                    }
                }
                
                // Add scroll-based animation for cards
                const cardMenu = document.querySelector('.card-menu');
                if (cardMenu && scrollY > 100) {
                    const translateFactor = Math.min((scrollY - 100) * 0.12, 60); /* how far past 100px has user scrolled, mevement of menu icreases,capped at 60px up */
                    cardMenu.style.transform = `translateY(${-translateFactor}px)`; /* Moves elememt up as scroll increases */
                } else if (cardMenu) {
                    cardMenu.style.transform = 'translateY(0)';
                }

                const movieMenu = document.querySelector('.movie-calendar');
                if(movieMenu && scrollY > 100){
                    const translateFactor = Math.min((scrollY - 100)*0.12, 60);
                    movieMenu.style.transform = `translateY(${-translateFactor}px)`;
                } else if (movieMenu){
                    movieMenu.style.transform = 'translateY(0)';
                }
            });
            
            // Get all cards in the card menu and observe them
            if (cardContainer) {
                cards = cardContainer.querySelectorAll('.card2');
                cards.forEach(card => cardObserver.observe(card));
            }
            if(movieContainer){
                movies = movieContainer.querySelectorAll('.card');
                movies.forEach(movie => movieObserver.observe(movie));
            }
        }
    });
</script>
<div class="changing-background2">
    <div class="overlay"></div>
</div>
<div class="content">
    <h1 class="reveal-text">No Signal Media</h1>
    <p class="reveal-text"> some cool fance text about our website, what we do etc</p>   
</div>
<div class="parallax-container">
    <div class="card-backdrop"></div>
    <div class="card-menu" bind:this={cardContainer}>
        <Card2 title="News" description="What's new?" image="./news_icon.png"/>
        <Card2 title="Articles" description="blablablabla" image="./articles_icon.png"/>
        <Card2 title="Reviews" description="blablabla" image="./reviews_icon.png"/>
    </div>
</div>

<div class="parallax-container2">
    <div class="movie-backdrop"></div>
<div class="movie-calendar">
<div class="content2">
<h2 class="reveal-text">Your Movie Calendar:</h2>
<h2 class="reveal-text">What's Coming to Theaters This Month</h2>
</div>
<div class="cinema-news" bind:this ={movieContainer}>
    <a href="/Mickey17" class="mickey17-link">
    <Card title="Mickey 17" description="On a mission to survive the impossible!" image="./Mickey_17.jpg"/>
</a>
    <Card title="A Minecraft Movie" description="Block by block, adventure awaits!" image="./a_minecraft_movie.jpg"/>
    <Card title="The Alto Kings" description="Starring legendary Robert De Niro" image="./the_alto_kings.jpg"/>
    <Card title="The Monkey" description="Based on Stephen King's 1980 story" image="./the_monkey.jpg"/>
    <Card title="Bridget Jones: Mad About the Boy" description="She's back!" image="./bridget_jones.jpg"/>
</div>
</div>
</div>


<style>
  
    h1,p{
        color:white;
    }

    /* Second background (GIF animation) */
    .changing-background2 {
        position: fixed; /* Fixed position for the background */
        width: 100%;
        height: 100vh;
        z-index: 1;
        top: 0;
        left: 0;
        background-size: cover;
        background-position: center;
        animation: gifs 25s infinite steps(1);
        overflow: hidden;
    }
    
    .content{
        position: relative;
        z-index: 3; /* Increased z-index to be above background */
        padding: 4rem 2rem;
        max-width: 1200px;
        margin: 0 auto;
        min-height: 80vh; /* Increased to provide more space before cards appear */
        display: flex;
        flex-direction: column;
        justify-content: center;
        pointer-events: auto; /* Enable clicks on the content */
        transition: transform 0.5s ease, opacity 0.5s ease;
        will-change: transform, opacity;
    }
    .content2{
        position: relative;
        z-index: 3; /* Increased z-index to be above background */
        padding: 4rem 2rem;
        max-width: 1200px;
        margin: 0 auto;
        min-height: 60vh; /* Increased to provide more space before cards appear */
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        pointer-events: auto; /* Enable clicks on the content */
        transition: transform 0.5s ease, opacity 0.5s ease;
        will-change: transform, opacity;
    }
     
    .overlay {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: linear-gradient(to bottom, 
            rgba(0,0,0,0.2) 0%,
            rgba(0,0,0,0.4) 60%, 
            rgba(0,0,0,0.7) 100%);
        z-index: 2;
    }
    
    .content h1, .content p {
        pointer-events: auto; /* Re-enable clicks on text */
    }
    .content2 h2{
        pointer-events: auto;
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
    
    .content p {
        animation-delay: 0.5s;
    }

.content2 h2:first-child {
    animation-delay: 0.2s;
}

.content2 h2:last-child {
    animation-delay: 0.5s;
}
    .content h1:hover{
        text-shadow: 0 0 25px rgba(255, 255, 255, 0.5);
        transform: scale(1.02);
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

    @keyframes gifs {
        0%, 13% { 
            background-image: url('/oppenheimer.gif');
        }
      
        15%, 32% { 
            background-image: url('/american_psycho.gif');
        }
       
        34%, 39% { 
            background-image: url('/neverending_story.gif');
        }
      
        41%, 44% { 
            background-image: url('/psycho.gif');
        }
      
        46%, 52% { 
            background-image: url('/forest_gump.gif');
        }
     
        54%, 63% { 
            background-image: url('/inception.gif');
        }
        
        65%, 70% { 
            background-image: url('/shutter_island.gif');
        }
       
        72%, 80% { 
            background-image: url('/django_unchained.gif');
        }
       
        81%, 86% { 
            background-image: url('/pulp_fiction.gif');
        }
        
        88%, 92% { 
            background-image: url('/joker.gif');
        }
       
        93%, 100% { 
            background-image: url('/silence_of_the_lambs.gif');
        }
    }
    .parallax-container {
        position: relative;
        z-index: 5; /* Lower z-index so it appears between content and movie-calendar */
        padding: 3rem 0;
        overflow: visible; /* Allow content to be visible outside container */
        margin-top: -20vh; /* Adjusted to start appearing as you scroll down */
        transition: transform 0.8s ease-in-out;
        will-change: transform;
        min-height: 50vh; /* Ensure enough height for scrolling effect */
    }
    .parallax-container2 {
        position: relative;
        z-index: 5; /* Lower z-index so it appears between content and movie-calendar */
        padding: 3rem 0;
        overflow: visible; /* Allow content to be visible outside container */
        margin-top: 20vh;
        transition: transform 0.8s ease-in-out;
        will-change: transform;
        min-height: 50vh; /* Ensure enough height for scrolling effect */
    }
    .card-backdrop {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        backdrop-filter: blur(8px);
        background-color: rgba(0, 0, 0, 0.4);
        z-index: -1;
        border-radius: 30px;
        transition: backdrop-filter 0.5s ease, background-color 0.5s ease;
        box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        margin: 0 2rem; /* Add margin for better visual appearance */
        width: calc(100% - 4rem); /* Adjust width to account for margin */
    }
    .movie-backdrop {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        backdrop-filter: blur(8px);
        background-color: rgba(255, 255, 255, 0.4);
        z-index: -1;
        border-radius: 30px;
        transition: backdrop-filter 0.5s ease, background-color 0.5s ease;
        box-shadow: 0 20px 40px rgba(226, 226, 226, 0.3);
        margin: 0 2rem; /* Add margin for better visual appearance */
        width: calc(100% - 4rem); /* Adjust width to account for margin */
    }
    
    .parallax-container:hover .card-backdrop {
        backdrop-filter: blur(12px);
        background-color: rgba(0, 0, 0, 0.5);
    }
    .parallax-container:hover .card-menu {
        perspective: 1500px; /* Increase perspective on hover */
    }
    
    
    .card-menu {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 30px;
        margin: 4rem 2rem 0 2rem; /* Adjusted margins for better spacing */
        padding: 3rem 2rem;
        place-items: center;
        position: relative;
        z-index: 20;
        transform-style: preserve-3d;
        perspective: 1000px;
        background-color: rgba(0, 0, 0, 0.2);
        border-radius: 30px;
        transition: transform 0.5s ease, background-color 0.5s ease;
        max-width: 1200px; /* Set max width for better appearance on wide screens */
        margin-left: auto;
        margin-right: auto;
    }
    
    :global(.cinema-news .card) {
    opacity: 1; /* Make sure opacity is 1 when the cards are visible */
}

    
    :global(.card-menu .card2)  :global(.cinema-news .card) {
        transform: translateY(60px);
        opacity: 0;
        transition: transform 0.8s ease-out, opacity 0.8s ease-out, box-shadow 0.3s ease;
        box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        will-change: transform, opacity;
        backface-visibility: hidden; /* Improve performance */
        -webkit-backface-visibility: hidden;
    }
    
    
    :global(.card-menu > .card2:first-child)
    {
        background-color:rgb(220, 224, 95);
    }
    :global(.card-menu > .card2:nth-child(2))
    {
        background-color:rgb(86, 205, 223);
    }

    :global(.card-menu > .card2:last-child)
    {
        background-color:rgb(214, 86, 80);
    }
    .movie-calendar{
        background-color:rgba(255, 255, 255);
        border-radius:50px;
        position: relative;
        z-index: 10; /* Higher z-index to appear above the cards */
        margin-top: 40px; /* Increased margin for better spacing */
        padding: 10px;
        box-shadow: 0 -10px 40px rgba(0, 0, 0, 0.1);
        max-width: 1200px;
        margin-left: auto;
        margin-right: auto;
    }
    .content2 h2{
        font-size: 60px;
        text-shadow: 0 0 15px rgba(255, 255, 255, 0.3);
        transition: text-shadow 0.3s ease, transform 0.3s ease;
        
    } 
    .cinema-news{
        background-color: rgba(154, 154, 154, 0.6);
        border-radius:50px;
        position:relative;
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(220px,1fr));
        margin-top:10px;
        place-items: center;
    }
  /*  
    .gallery-container
    {
        background-color:rgb(215, 213, 210);
        padding:2rem;
        border-radius: 50px;
    }

     
      .gallery {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        gap: 40px; 
        margin-top: 2rem;
    }

    .gallery::before {
        font-size: 1.5rem;
        font-weight: bold;
    }


    .gallery::after {
        content:"";
        width:60%;
        height:3px;
        background: linear-gradient(to right, rgb(102, 225, 188), transparent);
        
}
.text-content-gallery{
    display:flex;
    justify-content: left;
    align-items: center;
}

.text-content-gallery h2{
    font-size: 70px;
    background: linear-gradient(to right, rgb(22, 234, 128), rgb(234, 22, 199));
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
}
:global(.gallery> .card:hover ~ .card) {
        transform: scale(0.9);
        opacity: 0.8;
    }
*/
</style>
