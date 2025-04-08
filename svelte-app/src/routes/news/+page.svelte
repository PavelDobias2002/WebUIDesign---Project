<script>
import { onMount } from 'svelte';

import { scale } from 'svelte/transition';

// import base to prefix local paths
import { base } from '$app/paths';

// data for each news
let allNews = [
    {
        "id": 1,
        "title": "Nosferatu",
        "subtitle": "Spongebob's favourite vampire",
        "content": "Tim Burton’s The Nightmare Before Christmas (1993) is a unique blend of dark gothic aesthetics and whimsical fairytale charm. The film follows Jack Skellington, the Pumpkin King of Halloween Town, who discovers Christmas Town and decides to bring holiday cheer—though with a spooky twist.",
        "author": "Pavel Dobias",
        "date": "29/03/2025"
    },
    {
        "id": 2,
        "title": "Writers Strike!",
        "subtitle": "What this means to Hollywood",
        "content": "The ongoing writers' strike has brought Hollywood to a standstill, delaying major productions and TV shows. Writers are demanding better pay and improved working conditions, while studios struggle to negotiate a deal. The industry faces uncertainty as both sides remain firm in their positions.",
        "author": "Pavel Dobias",
        "date": "29/03/2025"
    },
    {
        "id": 3,
        "title": "Godzilla x Kong: The New Empire",
        "subtitle": "The MonsterVerse continues",
        "content": "The titanic duo of Godzilla and King Kong teams up against a mysterious new enemy in *Godzilla x Kong: The New Empire*. With bigger action, new creatures, and an expanded MonsterVerse, this sequel aims to be a massive cinematic event.",
        "author": "Pavel Dobias",
        "date": "05/04/2025"
    },
    {
        "id": 4,
        "title": "Dune: Part Two",
        "subtitle": "The sci-fi epic returns",
        "content": "Denis Villeneuve’s *Dune: Part Two* continues the journey of Paul Atreides, played by Timothée Chalamet. With stunning visuals and an expanded cast, the film promises to be even more ambitious than its predecessor.",
        "author": "Pavel Dobias",
        "date": "05/04/2025"
    },
    {
        "id": 5,
        "title": "The Batman 2",
        "subtitle": "Robert Pattinson returns as the Dark Knight",
        "content": "Matt Reeves is set to direct *The Batman 2*, continuing his gritty take on Gotham. Fans are speculating about the main villain—will Barry Keoghan’s Joker take the spotlight, or will a new threat emerge?",
        "author": "Pavel Dobias",
        "date": "05/04/2025"
    },
    {
        "id": 6,
        "title": "Joker: Folie à Deux",
        "subtitle": "Joaquin Phoenix and Lady Gaga in a twisted musical",
        "content": "Todd Phillips returns with *Joker: Folie à Deux*, a unique psychological thriller that leans into musical elements. Joaquin Phoenix reprises his role as Arthur Fleck, joined by Lady Gaga as Harley Quinn in a film promising to be as unsettling as it is captivating.",
        "author": "Pavel Dobias",
        "date": "05/04/2025"
    }
];

let news = [...allNews];

</script>
<div class="overlay"></div> <!--Overlay over the page background creating subtle gradient-->
<div class="header-container">  <!--Header with titles-->
    <h1 class="reveal-text">News News and more News!</h1>
    <h2 class="reveal-text">From Cinema to your screen.</h2>
</div>

{#if news.length > 0}   <!--if there are any news within the array-->
		<div class="news-container">

			{#each news as news (news.id)} <!--check for the ids based on the input-->

				<div class="news-article">

					<div class="title">
						<a href="{base}/newsArticle">
                            <h3>{news.title}</h3>
                            <h4>{news.subtitle}</h4>
                            </a>
					</div>

					<div class="paragraph">
						<a href="{base}/newsArticle">
                            <p>{news.content}</p>
                            </a>
					</div>

					<div class="date">
						<h3>Date:</h3>
		                <p>{news.date}</p>
                        <h3>Editor:</h3>
                        <p>{news.author}</p>
					</div>
				</div>
			{/each}
		</div>
	{/if}

<style>

.overlay 
{  /*the gradient on the page background*/
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

.header-container h1
{   /*Style for the main heading*/
    font-family: 'Pixelify Sans', sans-serif;
    font-optical-sizing: auto;
    font-weight: 700;
    font-style: normal;
    color: var(--news-color);   
    padding-top:5%;
}

.reveal-text 
{
    opacity: 0;
    transform: translateY(20px);
    animation: revealText 1s forwards ease-out;
}

@keyframes revealText 
{
    0% {
        opacity: 0;
        transform: translateY(50px);
    }
 

    100% {
        opacity: 1;
        transform: translateY(0);
    }
}

.header-container h2
{ /*style for sub heading*/
    font-family: "Exo 2", sans-serif;
    font-optical-sizing: auto;
    font-weight: 500;
    font-size: 4rem;
    font-style: normal;
    border-bottom: 4px solid var(--news-color);
}

.news-container h3
{ /*Style for heading within the news article divs*/
	font-family: "Exo 2", sans-serif;
    font-optical-sizing: auto;
    font-weight: 700;
    font-style: normal;
    font-size: 2rem;

    border-bottom: 2px solid var(--news-color);
		
	letter-spacing: 2px;
	text-transform: uppercase;
}

.news-container h4
{ /*Style for heading within the news article divs*/
	font-family: "Exo 2", sans-serif;
    font-optical-sizing: auto;
    font-weight: 500;
    font-style: normal;
    font-size: 1.5rem;
}
	
.news-container p
{ /*Style for paragraphs within the news article divs*/
	font-family: "Exo 2", sans-serif;
    font-optical-sizing: auto;
    font-weight: 500;
    font-style: normal;
    font-size: 1.25rem;
}

.news-container > div
{ /*referfers to each div that is within the news container*/
	background-color: rgba(16, 16, 16, 0.6);
	border-radius:30px;
	padding:1.5rem;
}

.news-article:hover 
{   /*When hover on the article it goes up to emphasize clickability*/
    margin-top: 5px;
    transform: translateY(-10px);
    border-bottom: 10px solid var(--news-color);
    box-shadow: 0 5px 15px rgba(0,0,0,0.2);
}

/* Base layout (desktop first) */
.news-container 
{
    display: grid;
    grid-template-columns: repeat(1, 1fr); 
    grid-template-rows: auto auto auto;
    gap: 2rem;
    padding: 2rem;
    width: 80%;
    max-width: 1600px;
    margin: auto;
}

.news-article 
{
    display: grid;
    grid-template-columns: 2fr 4fr 1fr;
    gap: 1.5rem;
    border-bottom: 3px solid var(--news-color);
    border-left: 3px solid var(--news-color);
    transition: all 0.3s ease;
}

/* Base article layout (desktop) */
.title 
{
    grid-area: 1 / 1 / 1 / 2;
    border-right: 2px solid rgba(62, 62, 62, 0.3);
    padding-right: 1rem;
    text-align: left;
}

.paragraph 
{
    grid-area: 1 / 2 / 1 / 2;
    padding: 0 1rem;
    text-align: left;
}

.date 
{
    grid-area: 1 / 3 / 1 / 3;
    text-align: right;
    border-left: 2px solid rgba(62, 62, 62, 0.3);
    padding-left: 1rem;
}

/* Hover effects for desktop */
.news-article:hover 
{
    margin-top: 5px;
    transform: translateY(-10px);
    border-bottom: 10px solid var(--news-color);
    box-shadow: 0 5px 15px rgba(0,0,0,0.2);
}

/* Tablet breakpoint (max-width: 1024px) */
@media screen and (max-width: 64em) 
{
    .news-container {
        width: 90%;
        padding: 1.5rem;
    }

    .news-article {
        grid-template-columns: 1fr 2fr;
        grid-template-rows: auto auto;
    }

    .title {
        grid-area: 1 / 1 / 2 / 2;
    }

    .paragraph {
        grid-area: 1 / 2 / 2 / 3;
    }

    .date {
        grid-area: 2 / 1 / 3 / 3;
        text-align: right;
        border-left: none;
        border-top: 2px solid rgba(62, 62, 62, 0.3);
        padding-top: 1rem;
    }

    .header-container h2 {
        font-size: 3rem;
    }
}

/* Mobile breakpoint (max-width: 768px) */
@media screen and (max-width: 48em) 
{
    .news-container {
        width: 95%;
        padding: 1rem;
    }

    .news-article {
        grid-template-columns: 1fr;
        grid-template-rows: auto auto auto;
        gap: 1rem;
    }

    .title {
        grid-area: 1 / 1 / 2 / 2;
        border-right: none;
        border-bottom: 2px solid rgba(62, 62, 62, 0.3);
        padding: 0 0 1rem 0;
        text-align: center;
    }

    .paragraph {
        grid-area: 2 / 1 / 3 / 2;
        padding: 1rem 0;
        border-bottom: 2px solid rgba(62, 62, 62, 0.3);
    }

    .date {
        grid-area: 3 / 1 / 4 / 2;
        text-align: center;
        border-top: none;
        padding-top: 1rem;
    }

    /*smaller text for mobile*/
    .header-container h1 {
        font-size: 2.5rem;
    }

    .header-container h2 {
        font-size: 2rem;
    }

    .news-container h3 {
        font-size: 1.75rem;
    }

    .news-container h4 {
        font-size: 1.25rem;
    }

    .news-container p {
        font-size: 1rem;
    }
}

</style>