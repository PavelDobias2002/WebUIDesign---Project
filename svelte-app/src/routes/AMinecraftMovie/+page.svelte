<script>

</script>
<div class="overlay"></div>
<div class="header-container">
    <h1 class="reveal-text">Movie Calendar</h1>
    <h2 class= "reveal-text">A Minecraft Movie</h2>
</div>

<div class="movie-container">
	<div class="image">
		<img src='/a_minecraft_movie.jpg' alt="A Minecraft Movie movie poster">
	</div>
	<div class="title">
		<h3>A Minecraft Movie</h3>
	</div>
	<div class="genre">
		<h3>genre:</h3>
		<p> Kids & Family/Adventure/Fantasy/Action</p>
	</div>
	<div class="director">
		<h3>director:</h3>
		<p>Jared Hess</p>
	</div>
	<div class="production">
		<h3>production:</h3>
		<p>	Legendary Pictures</p>
			<p>Mojang Studios</p>
			<p>Vertigo Entertaiment<p>
            <p>Ont the Roam</p>
			<p>Domain Entertainment</p>
	</div>
	<div class="cast">
		<h3>cast:</h3>
		<p>Jason Momoa</p>
		<p>Jack Black</p>
		<p>Danielle Brooks</p>
		<p>Emma Myers</p>
		<p>Sebastian Hansen</p>
	</div>
	<div class="cinemasIreland">
		<h3>Premiere in April 4rd!</h3>
		<p>Write it down and don't forget!</p>
	</div>


	<div class="description">
		<h3>Description:</h3>
		<p>Four misfits – Garrett “The Garbage Man” Garrison (Jason Momoa), Henry (Sebastian Hansen), Natalie (Emma Myers) and Dawn (Danielle Brooks) – find themselves struggling with ordinary problems when they are suddenly pulled through a mysterious portal into the Overworld: the bizarre, blocky wonderland that we know and mine extensively love. To get back home, they’ll have to master this world (and protect it from evil things like piglins and zombies, too) while embarking on a magical quest with an unexpected, expert crafter, Steve (Jack Black). Together, their adventure will challenge all five to be bold and to reconnect with the qualities that make each of them uniquely creative…the very skills they need to thrive back in the real world.</p>
	</div>
	<div class="trailer">
		<h3>trailer</h3>
		<iframe src="https://www.youtube.com/embed/wJO_vIDZn-I?si=WSIFNRfCq06Bl19P"></iframe>
	</div>
	
</div>

<style>
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
	.header-container h1{
		transition: text-shadow 0.3s ease, transform 0.3s ease;
        animation-delay: 0.2s;
	}
	.header-container h2{
		transition: text-shadow 0.3s ease, transform 0.3s ease;
        animation-delay: 0.5s;
	}

	.movie-container .title h3{
		font-size: 3.5rem;
		color:black;
		letter-spacing: 2px;
		text-transform: uppercase;
	}
	
    .movie-container h3 {
        font-size: 2rem;
        color: #e6e6e6;
        text-transform: capitalize;
    }
	.movie-container p{
		font-size: 0.9rem;
	}
	.movie-container > div{
		background-color: rgba(104, 165, 106, 0.6);
		border-radius:30px;
		padding:1rem;
        box-shadow: 0 0 15px rgba(212, 212, 212, 0.3);
	}
    .movie-container{
        display: grid;
        grid-template-columns: repeat(6, 1fr);
        grid-template-rows: auto auto auto auto ;
        gap: 30px;
		padding:20px;
        width:80%;
        margin:auto;
		
    }

.image {
	grid-area: 1 / 1 / 4 / 4; /*row start column start/row end column end*/
}
.image img{
	border-radius: 30px;
	width:100%;
	height:100%;
	object-fit: cover;
}
.title {
	grid-area: 1 / 4 / 1 / 7;
	
}
.genre {
	grid-area: 2/4/3/5;
	
}
.director {
	grid-area: 3/4/4/5;
	height:50%;
}
.production {
	grid-area: 3/5/4/6;
}
.cast {
	grid-area: 2 / 6 / 4 / 7;
	
}
.cast p{
	margin-bottom:50px;
}
.cinemasIreland {
	grid-area: 2/5/3/6;
	
}
.description {
	grid-area: 4 / 1 / 7 / 5;
	
}
.trailer {
	grid-area: 4 / 5 / 7 / 7;
	overflow:hidden;
	position:relative;
}
.trailer iframe {
        width: 100%;  /* Make the iframe take up the full width of the container */
		height: 100%;
		position:absolute;
		top:0;
		left:0;
        border: none;
		border-radius: 30px;
        object-fit: cover; /* Makes the video cover the entire iframe while maintaining aspect ratio */
    }

	.reveal-text {
        opacity: 0;
        transform: translateY(20px);
        animation: revealText 1s forwards ease-out;
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