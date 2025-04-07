<script>
import { onMount } from 'svelte';

import { scale } from 'svelte/transition';

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
        content: 'a landmark in horror cinema. This silent film, loosely based on Dracula, introduces the unforgettable Count Orlok, played by Max Schreck, whose grotesque appearance and eerie performance have become iconic. The films use of shadows, distorted angles, and expressionist techniques creates a haunting atmosphere that lingers long after the credits roll. Murnaus masterful direction and Fritz Arno Wagners cinematography make Nosferatu a chilling, visually striking experience, and its influence on the horror genre is undeniable. Even after more than a century, it remains a terrifying and innovative classic.',
		genre: 'horror',
		director: 'Robert Eggers',
        author: 'Eliska Vrzalova',
        date: '2024'
    },
    {
        id: 3,
		image: 'mickey17poster.jpg',
        title: 'Mickey 17',
        rating: 9,
        content: 'a sci-fi film starring Robert Pattinson as Mickey Barnes, an "Expendable" worker on a distant planet who faces repeated deaths and rebirths. The film blends dark humor with themes of corporate exploitation and cloning. Critics have praised Pattinson’s performance, but the narrative is seen as uneven. While some find it a quirky, inventive film, others criticize its meandering plot and tonal inconsistencies. Overall, Mickey 17 is a unique and thought-provoking experience, though its complexity may not be for everyone.',
		genre: 'animated horror',
		director: 'Tim Burton',
        author: 'Pavel Dobias',
        date: '1994'
    },
    {
        "id": 4,
        "image": "thewhaleposter.jpg",
        "title": "The Whale",
        "rating": 8,
        "content": "A powerful drama starring Brendan Fraser as a reclusive English teacher who is struggling with obesity and trying to reconnect with his estranged daughter. The film is emotionally intense, with Fraser delivering a standout performance. While the story’s heaviness may be difficult for some, the film is a poignant exploration of redemption and self-worth.",
        "genre": "drama",
        "director": "Darren Aronofsky",
        "author": "Jake Kelly",
        "date": "2022"
    },
    {
        "id": 5,
        "image": "barbieposter.jpg",
        "title": "Barbie",
        "rating": 7,
        "content": "A visually vibrant comedy that brings the iconic doll to life in a satirical exploration of gender, identity, and societal expectations. Margot Robbie shines in the lead role, and the film’s playful yet insightful humor tackles contemporary issues. While it may not be for everyone, *Barbie* is a fresh take on the traditional family film.",
        "genre": "comedy, fantasy",
        "director": "Greta Gerwig",
        "author": "Pavel Dobias",
        "date": "2023"
    },
    {
        "id": 6,
        "image": "dunkirkposter.jpg",
        "title": "Dunkirk",
        "rating": 9,
        "content": "Christopher Nolan’s gripping World War II thriller, which chronicles the evacuation of British troops from Dunkirk, France. With minimal dialogue and a relentless sense of urgency, the film immerses viewers in the chaos and heroism of war. The impeccable cinematography, Hans Zimmer’s score, and stellar performances make *Dunkirk* a breathtaking cinematic experience.",
        "genre": "war, thriller",
        "director": "Christopher Nolan",
        "author": "Eliska Vrzalova",
        "date": "2017"
    },
    {
        "id": 7,
        "image": "spiderverseposter.jpg",
        "title": "Spider-Man: Into the Spider-Verse",
        "rating": 10,
        "content": "A groundbreaking animated superhero film that brings together multiple versions of Spider-Man from various dimensions. With stunning animation, a compelling storyline, and fantastic voice performances, *Into the Spider-Verse* revolutionized the genre and set a new standard for animated films. It’s a vibrant, emotional, and visually spectacular experience.",
        "genre": "animated, action",
        "director": "Bob Persichetti, Peter Ramsey, Rodney Rothman",
        "author": "Jake Kelly",
        "date": "2018"
    },
    {
        "id": 8,
        "image": "herposter.jpg",
        "title": "Her",
        "rating": 8,
        "content": "A thought-provoking sci-fi romance that follows a man who develops a relationship with an artificial intelligence operating system. Directed by Spike Jonze, *Her* is a meditative exploration of loneliness, love, and human connection in a digital age. Joaquin Phoenix’s heartfelt performance, combined with the film’s beautiful visuals and score, makes this an unforgettable film.",
        "genre": "sci-fi, romance",
        "director": "Spike Jonze",
        "author": "Pavel Dobias",
        "date": "2013"
    },
    {
        "id": 9,
        "image": "shutterislandposter.jpg",
        "title": "Shutter Island",
        "rating": 8,
        "content": "A psychological thriller directed by Martin Scorsese, starring Leonardo DiCaprio as a U.S. Marshal investigating the disappearance of a patient from a mental institution on an isolated island. With a twisting narrative, eerie atmosphere, and a shocking climax, *Shutter Island* keeps viewers on the edge of their seats throughout.",
        "genre": "thriller, mystery",
        "director": "Martin Scorsese",
        "author": "Jake Kelly",
        "date": "2010"
    },
    {
        "id": 10,
        "image": "madmaxfuryroadposter.jpg",
        "title": "Mad Max: Fury Road",
        "rating": 9,
        "content": "An explosive, high-octane action film set in a dystopian wasteland, directed by George Miller. Tom Hardy stars as Max, who teams up with Imperator Furiosa (Charlize Theron) to escape a tyrannical warlord. With stunning practical effects, relentless action sequences, and a visually stunning world, *Mad Max: Fury Road* is a modern action classic.",
        "genre": "action, adventure",
        "director": "George Miller",
        "author": "Eliska Vrzalova",
        "date": "2015"
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
    <h1 class="reveal-text">Reviews</h1>
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
						<a href="">
						<img class="image1" src={review.image} alt = "image">
						</a>
					</div>

					<div class="paragraph">
						<a href="">
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

/*search bar styles*/
.search-container 
{
	margin-top: 2rem;
	margin-bottom: 1rem;
	font-family: "Exo 2", sans-serif;
}

.search-bar 
{
	display: flex;
	position: relative;
	max-width: 1000px;
	margin: 0 auto;
}

.search-bar input 
{
	flex: 1;
	padding: 12px 15px;
	border: 2px solid var(--reviews-color);
	border-radius: 4px 0 0 4px;
	font-size: 16px;
	outline: none;
	transition: border-color 0.3s;
}

.search-bar input:focus 
{
	border-color: var(--reviews-color);
}

.search-button 
{
	background-color: var(--reviews-color);
	border: none;
	padding: 12px 20px;
	border-radius: 0 4px 4px 0;
	cursor: pointer;
	font-size: 16px;
	transition: background-color 0.3s;
}

.search-button:hover 
{
	background-color: #357ac5;
}

.search-results 
{
	margin-top: 10px;
	text-align: center;
	color: #666;
	font-size: 14px;
}

/* Responsive design for search bar */

@media (max-width: 480px) 
{

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

}

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

.reviews-container 
{
	max-width: 1200px;
	margin: 0 auto;
	padding: 20px;
}

.header-container h1
{   /*Style for the main heading*/
	padding-top: 5%;
	text-align: center;
	align-items: center;
    font-family: 'Pixelify Sans', sans-serif;
    font-optical-sizing: auto;
    font-weight: 700;
    font-style: normal;
	color: var(--reviews-color);
	border-bottom: 4px solid var(--reviews-color);
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

.reviews-container h1
{ /*Style for heading within the news article divs*/
	font-family: "Exo 2", sans-serif;
    font-optical-sizing: auto;
    font-weight: 700;
    font-style: normal;
    font-size: 4rem;

    border-bottom: 2px solid var(--reviews-color);
		
	letter-spacing: 2px;
	text-transform: uppercase;
}

.reviews-container h3
{ /*Style for heading within the news article divs*/
	font-family: "Exo 2", sans-serif;
    font-optical-sizing: auto;
    font-weight: 700;
    font-style: normal;
    font-size: 2rem;

    border-bottom: 2px solid var(--reviews-color);
		
	letter-spacing: 2px;
	text-transform: uppercase;
}
	
.reviews-container p
{ /*Style for paragraphs within the news article divs*/
	font-family: "Exo 2", sans-serif;
    font-optical-sizing: auto;
    font-weight: 500;
    font-style: normal;
    font-size: 1.25rem;
}

.reviews-container > div
{ /*referfers to each div that is within the news container*/
	background-color: rgba(16, 16, 16, 0.6);
	border-radius:30px;
	padding:1.5rem;
}

.reviews-container
{    /*the grid system used for the news container*/
    display: grid;
    grid-template-columns: repeat(1, 1fr); 
    grid-template-rows: auto auto auto;
    gap: 2rem;
	padding:2rem;
    width:80%;
    max-width: 1600px;
    margin:auto;
}

.review-item
{ /*grid system for the news articles*/
    display: grid;
    grid-template-columns: 2fr 4fr 1fr;
    gap: 1.5rem;
    transition: all 0.3s ease;
    border: 2px solid var(--reviews-color);
    box-shadow: 0 5px 15px rgba(0,0,0,0.2);
}

.review-heading:hover
{
	color: var(--reviews-color);
}

.review-footer 
{
	border-top: 2px solid var(--reviews-color);
}


.image1
{
	border-radius: 10px;
	width:100%;
	height:100%;
	object-fit: cover;
    align-items: center;
}

.image1:hover 
{   /*When hover on the article it goes up to emphasize clickability*/
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
    padding-left: 2rem;
}

/* Tablet breakpoint (max-width: 1024px) */
@media screen and (max-width: 64em) {
    .reviews-container {
        width: 90%;
        padding: 1.5rem;
    }

    .review-item {
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
}

/* Mobile breakpoint (max-width: 768px) */
@media screen and (max-width: 48em) {
    .reviews-container {
        width: 95%;
        padding: 1rem;
    }

    .review-item {
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

    .reviews-container h3 {
        font-size: 1.75rem;
    }

    .reviews-container p {
        font-size: 1rem;
    }
}

</style>