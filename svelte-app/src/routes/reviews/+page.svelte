<script>
import { onMount } from 'svelte';

// data for each review
let allReviews = [
    {
        id: 1,
		image: 'nigthmarePoster.jpg',
        title: 'Nightmare Before Christmass',
        rating: 9,
        content: 'Tim Burton’s The Nightmare Before Christmas (1993) is a unique blend of dark gothic aesthetics and whimsical fairytale charm. The film follows Jack Skellington, the Pumpkin King of Halloween Town, who discovers Christmas Town and decides to bring holiday cheer—though with a spooky twist.',
		genre: 'animated horror',
		director: 'Tim Burton',
        author: 'Pavel Dobias',
        date: '1994'
    },
    {
        id: 2,
		image: 'nosferatuPoster.jpg',
        title: 'Nosferatu',
        rating: 7,
        content: 'An amazing movie!',
		genre: 'horror',
		director: 'Robert Eggers',
        author: 'Pavel Dobias',
        date: '2024'
    },
    {
        id: 3,
		image: 'nigthmare.jpg',
        title: 'Mickey 17',
        rating: 9,
        content: 'An amazing movie!',
		genre: 'animated horror',
		director: 'Tim Burton',
        author: 'Pavel Dobias',
        date: '1994'
    }
];

let reviews = [...allReviews];
let searchQuery = '';

// Search functionality
function handleSearch() {
    if (!searchQuery.trim()) {
        reviews = [...allReviews];
        return;
    }

    const query = searchQuery.toLowerCase();
    reviews = allReviews.filter(
        (review) =>
            review.title.toLowerCase().includes(query) ||
            review.content.toLowerCase().includes(query) ||
            review.author.toLowerCase().includes(query)
    );
}

</script>
<div class="overlay"></div> <!--Overlay over the page background creating subtle gradient-->
<div class="header-container">  <!--Header with titles-->
    <h1>Reviews</h1>
</div>

	<div class="search-container">
		<div class="search-bar">
			<input
				type="text"
				placeholder="Search reviews..."
				bind:value={searchQuery}
				on:input={handleSearch}
			/>
			<button class="search-button" on:click={handleSearch}>Search</button>
		</div>
		
		{#if reviews.length < allReviews.length}
			<p class="search-results">Found {reviews.length} results for "{searchQuery}"</p>
		{/if}
	</div>

	{#if reviews.length > 0}
		<div class="reviews-container">

			{#each reviews as review (review.id)}

				<div class="review-item">

					<div class="title">
						<a href="/newsArticle">
						<img class="image1" src={review.image} alt = "image">
						</a>
					</div>

					<div class="paragraph">
						<a href="/newsArticle">
						<h3 class="review-heading">{review.title}</h3>
						</a>
						<p>
							{review.content}
						</p>
					</div>

					<div class="date">
						<h1>{review.rating}</h1>
						<p><b>Director:</b><br>{review.director}</p>
						<p><b>Genre:</b><br>{review.genre}</p>
						<p><b>Date:</b><br>{review.date}</p>
						<p class="review-footer"><b>By:</b><br>{review.author}</p>
					</div>
				</div>
			{/each}
		</div>
	{/if}


    <!-- This layout is used for each news article div-->


<style>

.reviews-container {
		max-width: 1200px;
		margin: 0 auto;
		padding: 20px;
	}

	.search-container {
		margin-top: 2rem;
		margin-bottom: 1rem;
		font-family: "Exo 2", sans-serif;
	}

	.search-bar {
		display: flex;
		position: relative;
		max-width: 1000px;
		margin: 0 auto;
	}

	.search-bar input {
		flex: 1;
		padding: 12px 15px;
		border: 2px solid var(--reviews-color);
		border-radius: 4px 0 0 4px;
		font-size: 16px;
		outline: none;
		transition: border-color 0.3s;
	}

	.search-bar input:focus {
		border-color: var(--reviews-color);
	}

	.search-button {
		background-color: var(--reviews-color);
		border: none;
		padding: 12px 20px;
		border-radius: 0 4px 4px 0;
		cursor: pointer;
		font-size: 16px;
		transition: background-color 0.3s;
	}

	.search-button:hover {
		background-color: #357ac5;
	}

	.search-results {
		margin-top: 10px;
		text-align: center;
		color: #666;
		font-size: 14px;
	}

	/* Responsive adjustments */

	@media (max-width: 480px) {

		.search-bar {
			flex-direction: column;
		}

		.search-bar input {
			border-radius: 4px;
			margin-bottom: 10px;
		}

		.search-button {
			border-radius: 4px;
			width: 100%;
		}

		.clear-button {
			right: 10px;
		}
	}

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
        -webkit-text-stroke: 2px var(--reviews-color);
        color: transparent;
        transition: transform 0.3s ease;
        animation: strokeTransition 2s ease-in-out infinite alternate;
		border-bottom: 4px solid var(--reviews-color);
    }

    

    .header-container h2{ /*style for sub heading*/
        font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 500;
        font-size: 5rem;
        font-style: normal;
        border-bottom: 4px solid var(--reviews-color);
    }

	.reviews-container h1{ /*Style for heading within the news article divs*/
		font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 700;
        font-style: normal;
        font-size: 4rem;

        border-bottom: 2px solid var(--reviews-color);
		
		letter-spacing: 2px;
		text-transform: uppercase;
	}

	.reviews-container h3{ /*Style for heading within the news article divs*/
		font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 700;
        font-style: normal;
        font-size: 2rem;

        border-bottom: 2px solid var(--reviews-color);
		
		letter-spacing: 2px;
		text-transform: uppercase;
	}

    .reviews-container h4{ /*Style for heading within the news article divs*/
		font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 500;
        font-style: normal;
        font-size: 1.5rem;
		
		
	}
	
	.reviews-container p{ /*Style for paragraphs within the news article divs*/
		font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 500;
        font-style: normal;
        font-size: 1.25rem;

        
	}
	.reviews-container > div{ /*referfers to each div that is within the news container*/
		background-color: rgba(16, 16, 16, 0.6);
		border-radius:30px;
		padding:1.5rem;
	}
    .reviews-container{    /*the grid system used for the news container*/
        display: grid;
        grid-template-columns: repeat(1, 1fr); 
        grid-template-rows: auto auto auto;
        gap: 2rem;
		padding:2rem;
        width:80%;
        max-width: 1600px;
        margin:auto;
    }

    .review-item{ /*grid system for the news articles*/
        display: grid;
        grid-template-columns: 2fr 4fr 1fr;
        gap: 1.5rem;
        transition: all 0.3s ease;
        border: 2px solid var(--reviews-color);
        box-shadow: 0 5px 15px rgba(0,0,0,0.2);
    }

	.review-heading:hover{
		color: var(--reviews-color);
	}

	.review-footer {
		border-top: 2px solid var(--reviews-color);
	}


.image1{
	border-radius: 10px;
	width:100%;
	height:100%;
	object-fit: cover;
    align-items: center;
}

 .image1:hover {   /*When hover on the article it goes up to emphasize clickability*/
    border: 5px solid var(--reviews-color);
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
	grid-area: 1 / 3 / 1 / 8;
    text-align: right;
    border-left: 2px solid rgba(62, 62, 62, 0.3);
    padding-left: 1rem;
}

</style>