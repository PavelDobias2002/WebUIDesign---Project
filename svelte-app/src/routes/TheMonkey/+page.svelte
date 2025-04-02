<script>

</script>
<div class="overlay"></div>
<div class="header-container">
    <h1 class="reveal-text">Movie Calendar</h1>
</div>

<div class="movie-container">
	<div class="image">
		<img src='/the_monkey.jpg' alt="The Monkey movie poster">
	</div>
	<div class="title">
		<h3>The Monkey</h3>
	</div>
	<div class="genre">
		<h3>genre:</h3>
		<p>Horror/Splatter Horror/Dark Comedy</p>
	</div>
	<div class="director">
		<h3>director:</h3>
		<p>	Osgood Perkins</p>
	</div>
	<div class="production">
		<h3>production:</h3>
		<p>C2</p>
        <p>Atomic Monster</p>
        <p>The Safran Company</p>
        <p>Oddfellows</p>
        <p>Range</p>
        <p>Stars Collective </p>
	</div>
	<div class="cast">
		<h3>cast:</h3>
		<p>Theo James</p>
		<p>Tatiana Maslany</p>
		<p>Christian Convery</p>
		<p>Colin O'Brien</p>
		<p>Rohan Campbell</p>
        <p>Sarah Levy</p>
        <p>Adam Scott</p>
        <p>Elijah Wood</p>
	</div>
	<div class="cinemasIreland">
		<h3>Now in theaters!</h3>
		<p>Don't miss the opportunity now in any cinema in Ireland!</p>
	</div>


	<div class="description">
		<h3>Description:</h3>
		<p>Twin brothers Hal and Bill owned such a toy monkey as kids, and couldn’t help noticing that whenever it was around, parents and friends seemed to perish with alarming regularity, in various hideous ways. Just throw it away, right? Well, the brothers tried that, hacking up the cursed plaything with a cleaver then dropping it down a well. And that seemed to quell the bloodshed for a while. But in adulthood, the murders start back up with a vengeance – and they’re grislier than ever. To protect Hal and Bill’s own families, the stick-wielding simian must be stopped – but how?</p>
	</div>
	<div class="trailer">
		<h3>trailer</h3>
		<iframe src="https://www.youtube.com/embed/0BLUVCRKshw?si=sjuaowBtprYRzTHT"
		title="The Monkey trailer"
		frameborder="0" 
		allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
		allowfullscreen>
	</iframe>
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
		font-size: 1rem;
		font-family:"Exo 2", sans-serif;
	}
	.movie-container > div{
		background-color: rgba(126, 31, 31, 0.6);
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
        top:0;
        left:0;
        position:absolute;
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

	
	@media (max-width: 768px) {
		.header-container h1{
			font-size: 2.5rem;
		}
 		.movie-container {
 			grid-template-columns: 1fr;
 			gap:20px;
 			width:100%;
 			padding:2rem;
			 margin: 5vh auto;
 			background-color:  rgba(126, 31, 31, 0.6);
 			border-radius:30px;
			justify-content:center;
			place-items:center;
 		}
 		.movie-container > div p{
 			font-size:1.2rem;
 		}
		.movie-container > div{
			padding:0.3rem;
			max-width:90%;
			background-color: transparent;
			box-shadow: none;
			border-bottom: 4px solid rgb(27, 1, 1);
		}
 		.image{
 			grid-area: 2 / 1 / 3 / 2;
 		}
 		.title{
 			grid-area: 1 / 1 / 2 / 2;
 		}
 		.movie-container .title h3{
 			font-size: 2rem;
 		}
 		.genre{
 			grid-area: 3 / 1 / 4 / 2;
 		}
 		.director {
 			grid-area: 4 /1/5/2;
 			height: 100%;
 		}
 		.production {
 			grid-area: 5/1/6/2;
 		}
 		.cast {
 		grid-area: 6 / 1 / 7 / 2;
 	
 		}
 		.cinemasIreland {
 		grid-area: 7/1/8/2;
 	
 		}
 		.description {
 		grid-area: 8 / 1 / 9 / 2;
 	
 		}
 	.trailer {
 	grid-area: 9 / 1 / 10 / 2;
 	overflow:hidden;
 	position:relative;
	width:100%;
	height: 350px;
 	}
	.trailer iframe{
		width:100%;
		height: 100%;
		position: relative;
	}


	}

	@media (min-width: 768px) and (max-width: 1024px) {

	.header-container h1{
		font-size: 3rem;
	}
    .movie-container {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 20px;
        width: 90%;
        margin: 2rem auto;
        padding: 1.5rem;
    }
    
    .title {
        grid-area: 1 / 1 / 2 / 3;
        text-align: center;
    }
    
    .image {
        grid-area: 2 / 1 / 3 / 3;
        width: 100%;
        height: auto;
    }
    
    .genre {
        grid-area: 3 / 1 / 4 / 2;
    }
    
    .director {
        grid-area: 3 / 2 / 4 / 3;
    }
    
    .production {
        grid-area: 4 / 1 / 5 / 2;
    }
    
    .cast {
        grid-area: 4 / 2 / 5 / 3;
    }
	.cinemasIreland{
		grid-area: 5 / 1 / 6 / 3;
	}
    
    .description {
        grid-area: 6 / 1 / 7 / 3;
    }
    
    .trailer {
        grid-area: 7 / 1 / 8 / 3;
		position:relative;
		width:100%;
        height: 400px;
    }
	.trailer iframe{
		width:100%;
		height: 100%;
		position: relative;
	}
    .movie-container .title h3 {
        font-size: 2.5rem;
    }
    
    .movie-container > div {
        height: auto;
        min-height: fit-content;
		box-shadow: 0 0 15px rgba(212, 212, 212, 0.3);
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
    }
    
    .movie-container > div h3 {
        margin-bottom: 1rem;
    }
    
    .movie-container > div p {
        margin: 0.5rem 0;
		font-size: 1.5rem;
    }
}

</style>