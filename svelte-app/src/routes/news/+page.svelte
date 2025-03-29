<script>
import { onMount } from 'svelte';

// data for each news
let allNews = [
    {
        id: 1,
        title: 'Nosferatu',
        subtitle: 'Spongebob favourite vampire',
        content: 'Tim Burton’s The Nightmare Before Christmas (1993) is a unique blend of dark gothic aesthetics and whimsical fairytale charm. The film follows Jack Skellington, the Pumpkin King of Halloween Town, who discovers Christmas Town and decides to bring holiday cheer—though with a spooky twist.',
        author: 'Pavel Dobias',
        date: '29/03/2025'
    },
    {
        id: 2,
        title: 'Writers Strike!',
        subtitle: 'What this means to Hollywood',
        content: 'Writers hit the streets...',
        author: 'Pavel Dobias',
        date: '29/03/2025'
    },
    {
        id: 3,
        title: 'Nosferatu',
        subtitle: 'Spongebob favourite vampire',
        content: 'Tim Burton’s The Nightmare Before Christmas (1993) is a unique blend of dark gothic aesthetics and whimsical fairytale charm. The film follows Jack Skellington, the Pumpkin King of Halloween Town, who discovers Christmas Town and decides to bring holiday cheer—though with a spooky twist.',
        author: 'Pavel Dobias',
        date: '29/03/2025'
    }
];

let news = [...allNews];

</script>
<div class="overlay"></div> <!--Overlay over the page background creating subtle gradient-->
<div class="header-container">  <!--Header with titles-->
    <h1>News News and more News!</h1>
    <h2>From Cinema to your screen.</h2>
</div>

{#if news.length > 0}
		<div class="news-container">

			{#each news as news (news.id)}

				<div class="news-article">

					<div class="title">
						<a href="/newsArticle">
                            <h3>{news.title}</h3>
                            <h4>{news.subtitle}</h4>
                            </a>
					</div>

					<div class="paragraph">
						<a href="/newsArticle">
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
	    .overlay {  /*the gradient on the page background*/
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

    .header-container h1{   /*Style for the main heading*/
        font-family: 'Pixelify Sans', sans-serif;
        font-optical-sizing: auto;
        font-weight: 700;
        font-style: normal;
        -webkit-text-stroke: 2px var(--news-color);
        color: transparent;
        transition: transform 0.3s ease;
        animation: strokeTransition 2s ease-in-out infinite alternate;
    }

    

    .header-container h2{ /*style for sub heading*/
        font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 500;
        font-size: 4rem;
        font-style: normal;
        border-bottom: 4px solid var(--news-color);
    }

	.news-container h3{ /*Style for heading within the news article divs*/
		font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 700;
        font-style: normal;
        font-size: 2rem;

        border-bottom: 2px solid var(--news-color);
		
		letter-spacing: 2px;
		text-transform: uppercase;
	}

    .news-container h4{ /*Style for heading within the news article divs*/
		font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 500;
        font-style: normal;
        font-size: 1.5rem;
		
		
	}
	
	.news-container p{ /*Style for paragraphs within the news article divs*/
		font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 500;
        font-style: normal;
        font-size: 1.25rem;

        
	}
	.news-container > div{ /*referfers to each div that is within the news container*/
		background-color: rgba(16, 16, 16, 0.6);
		border-radius:30px;
		padding:1.5rem;
	}
    .news-container{    /*the grid system used for the news container*/
        display: grid;
        grid-template-columns: repeat(1, 1fr); 
        grid-template-rows: auto auto auto;
        gap: 2rem;
		padding:2rem;
        width:80%;
        max-width: 1600px;
        margin:auto;
    }

    .news-article{ /*grid system for the news articles*/
        display: grid;
        grid-template-columns: 2fr 4fr 1fr;
        gap: 1.5rem;
        border-bottom: 3px solid var(--news-color);
        border-left: 3px solid var(--news-color);
        transition: all 0.3s ease;
    }

    .news-article:hover {   /*When hover on the article it goes up to emphasize clickability*/
        margin-top: 5px;
        transform: translateY(-10px);
        border-bottom: 10px solid var(--news-color);
        box-shadow: 0 5px 15px rgba(0,0,0,0.2);
    }

/*where the elements of the news article are within the div*/
.title {
	grid-area: 1 / 1 / 1 / 2; /*row-start/ column-start/ row-end/ column-end/;*/
    border-right: 2px solid rgba(62, 62, 62, 0.3);
    padding-right: 1rem;
    text-align: left;
	
}

.paragraph{
    grid-area: 1 / 2 / 1 / 2;
    padding: 0 1rem;
    text-align: left;
}

.date {
	grid-area: 1 / 3 / 1 / 3;
    text-align: right;
    border-left: 2px solid rgba(62, 62, 62, 0.3);
    padding-left: 1rem;
}

</style>