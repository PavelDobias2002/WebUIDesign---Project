<script>

</script>
<div class="overlay"></div>
<div class="header-container">
    <h1>News News and more News!</h1>
    <h2>From Cinema to your screen.</h2>
</div>

<div class="news-container">
	
    <div class="news-article">

	    <div class="title">
		    <h3>Nosferatu hunts your dreams</h3>
	    </div>
	    
        <div class="paragraph">
            <p>The new adaptaion of legendary Vampire is set to be an amazing watch for you and your family.</p>

        </div>

        <div class="date">
		    <h3>Date:</h3>
		    <p>25/03/2025</p>
	    </div>
        
        <div class="container">

        </div>
    </div>
    
    <div class="news-article">

	    <div class="title">
		    <h3>Mickey 17 made a splash at the cinemas</h3>
	    </div>
	    
        <div class="paragraph">
            <p>​Bong Joon Ho's latest film, "Mickey 17," is a sci-fi satire starring Robert Pattinson as Mickey Barnes, an expendable crew member on a space colonization mission. In this dystopian future, Earth is plagued by environmental disasters, prompting a mission to colonize Niflheim. Mickey's role involves repeated dangerous tasks, resulting in his death and subsequent reprinting with retained memories.</p>

        </div>

        <div class="date">
		    <h3>Date:</h3>
		    <p>25/03/2025</p>
	    </div>
        
        <div class="container">

        </div>
    </div>

    <div class="news-article">

	    <div class="title">
		    <h3>Mickey 17</h3>
	    </div>
	    
        <div class="paragraph">
            <p>​Bong Joon Ho's latest film, "Mickey 17," is a sci-fi satire starring Robert Pattinson as Mickey Barnes, an expendable crew member on a space colonization mission. In this dystopian future, Earth is plagued by environmental disasters, prompting a mission to colonize Niflheim. Mickey's role involves repeated dangerous tasks, resulting in his death and subsequent reprinting with retained memories. </p>

        </div>

        <div class="date">
		    <h3>Date:</h3>
		    <p>25/03/2025</p>
	    </div>
        
        <div class="container">

        </div>
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

    .header-container h2{
        font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 500;
        font-style: normal;
    }

	.news-container h3{
		font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 700;
        font-style: normal;
        font-size: 2rem;
		color:black;
		letter-spacing: 2px;
		text-transform: uppercase;
	}
	
	.news-container p{
		font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 500;
        font-style: normal;

        
	}
	.news-container > div{
		background-color: rgba(154, 154, 154, 0.6);
		border-radius:30px;
		padding:1rem;
	}
    .news-container{
        display: grid;
        grid-template-columns: repeat(1, 1fr);
        grid-template-rows: auto auto auto;
        gap: 15px;
		padding:10px;
        width:80%;
        margin:auto;
		background-color: rgba(86, 94, 110, 0.6);
		border-radius:30px;
		box-shadow: 0 0 15px rgba(255, 255, 255, 0.3);
    }

    .news-article{
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-template-rows: auto;
    }

    .news-article::after{
        content: "";
            display: block;
            width: 40%;
            height: 2px;
            border-radius: 50px;
            margin: 0 auto 10px auto;
            transition: width 0.3s ease-in-out;
    }

    .news-article::before {
        content: attr(data-text);
        position: absolute;
        overflow:hidden;
        left:0;
        width:0;
        white-space: nowrap;
        transition:all 0.5s;
    }

.image {
	grid-area: 1 / 1 / 1/ 1; /*row start column start/row end column end*/
}
.image img{
	border-radius: 10px;
	width:100%;
	height:100%;
	object-fit: cover;
}
.title {
	grid-area: 1 / 1 / 1 / 2;
	
}

.paragraph{
    grid-area: 1 / 2 / 1 / 2;
}

.date {
	grid-area: 1 / 3 / 1 / 3;
}

.container{
    grid-area: 1 / 1 / 1 / 3;
    z-index: -1;
}

</style>