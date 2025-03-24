<script>

</script>

<div class="header-container">
    <h1>Movie Calendar</h1>
    <h2>Mickey 17</h2>
</div>

<div class="movie-container">
	<div class="image">
		<img src='/Mickey_17.jpg' alt="Mickey 17 movie poster">
	</div>
	<div class="title">
		<h3>Mickey 17</h3>
	</div>
	<div class="genre">
		<h3>genre:</h3>
		<p>Sci-Fi/Comedy/Drama/Mystery & Thriller</p>
	</div>
	<div class="director">
		<h3>director:</h3>
		<p>Bong Joon Ho</p>
	</div>
	<div class="production">
		<h3>production:</h3>
		<p></p>
	</div>
	<div class="cast">
		<h3>cast:</h3>
		<p>Robert Pattinson</p>
		<p>Mark Ruffalo</p>
		<p>Toni Collette</p>
		<p>Naomi Ackie</p>
		<p>Steven Yeun</p>
	</div>
	<div class="cinemasIreland">
		<h3>Now in theaters!</h3>
		<p></p>
	</div>
	<div class="description">
		<p>Robert Pattinson, wide-eyed and squeaky-voiced, is Mickey Barnes, who needs to get off-Earth sharpish. In the absence of any discernible skill set, he signs up as an “expendable”, and to be killed over and over again on a colony ship headed to the planet of Niflheim under the authority of monstrous politician and cult leader Kenneth Marshall (Mark Ruffalo) and his wife Ylfa (Toni Collette). All is fine, apart from the dying and being recreated by a “human printer”, and Mickey even strikes up a relationship with security officer Nasha (Naomi Ackie). But then, Mickey no. 17 unexpectedly survives a near-death experience, and gets home to find the new version of himself, Mickey 18, already up and about. It’s a scenario that means death for both, so Mickey must finally develop some wits and try and keep them about him.</p>
	</div>
	<div class="trailer">trailer</div>
</div>

<style>
	.movie-container h3{
		font-size: 30px;
	}
	.movie-container > div{
		background-color: rgb(109, 109, 109,0.3);
		border-radius: 40px;
	}
    .movie-container{
        display: grid;
        grid-template-columns: repeat(6, 1fr);
        grid-template-columns: repeat(5,1fr);
        gap: 30px;
		padding:20px;
        width:80%;
        margin:auto;
		background-color: rgb(179, 179, 179,0.4);
		border-radius: 50px;
		
    }

.image {
	grid-area: 1 / 1 / 4 / 3; /*row start column start/row end column end*/
}
.image img{
	border-radius: 50px;
}
.title {
	grid-area: 1 / 3 / 1 / 6;
	background-color: rgba(196,156,252, 0.5);
}
.genre {
	grid-area: 2/3/3/4;
	background-color: rgba(101,64,126, 0.5);
}
.director {
	grid-area: 3/3/4/4;
	background-color: rgba(60,76,23, 0.5);
}
.production {
	grid-area: 3/4/4/5;
	background-color: rgba(183,99,134, 0.5);
}
.cast {
	grid-area: 2 / 5 / 4 / 6;
	background-color: rgba(128,170,166, 0.5);
}
#cinemasIreland {
	grid-area: 2/4/3/5;
	background-color: rgba(68,247,44, 0.5);
}
.description {
	grid-area: 4 / 1 / 7 / 4;
	background-color: rgba(163,189,6, 0.5);
}
.trailer {
	grid-area: 4 / 4 / 7 / 6;
	background-color: rgba(6,85,199, 0.5);
}
</style>