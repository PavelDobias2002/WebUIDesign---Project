<script>

</script>

<div class="header-container">
    <h1>Movie Calendar</h1>
    <h2>Mickey 17</h2>
</div>

<div class="movie-container">
	<div class="image">image</div>
	<div class="title">title</div>
	<div class="genre">genre</div>
	<div class="director">director</div>
	<div class="production">production</div>
	<div class="cast">cast</div>
	<div class="cinemasIreland">cinemasIreland</div>
	<div class="description">description</div>
	<div class="trailer">trailer</div>
</div>

<style>
    .movie-container{
        display: grid;
        grid-template-columns: repeat(6, 1fr);
        grid-template-columns: repeat(5,1fr);
        gap: 40px;
        width:100%;
        height:100%;
    }

.image {
	grid-area: 1 / 1 / 4 / 3; /*row start column start/row end column end*/
	background-color: rgba(225,35,46, 0.5);
}
.title {
	grid-area: 1 / 3 / 2 / 6;
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