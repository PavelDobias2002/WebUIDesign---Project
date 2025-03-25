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
            <a href="/about">
		    <h3>Mickey 17 made a splash at the cinemas</h3>
            </a>
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

    .header-container h1{
        font-family: 'Pixelify Sans', sans-serif;
        font-optical-sizing: auto;
        font-weight: 700;
        font-style: normal;
        -webkit-text-stroke: 2px yellow;
        color: transparent;
        transition: transform 0.3s ease;
        animation: strokeTransition 2s ease-in-out infinite alternate;
    }

    

    .header-container h2{
        font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 500;
        font-size: 5rem;
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
		background-color: rgba(218, 218, 218, 0.6);
		box-shadow: 0 0 15px rgba(255, 255, 255, 0.3);
		border-radius:30px;
		padding:1.5rem;
	}
    .news-container{
        display: grid;
        grid-template-columns: repeat(1, 1fr);
        grid-template-rows: auto auto auto;
        gap: 30px;
		padding:2rem;
        width:80%;
        margin:auto;
    }

    .news-article{
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-template-rows: auto;
        border-bottom: 2px solid yellow;
        transition: all 0.3s ease;
    }

    .news-article:hover {
        margin-top: 5px;
        transform: translateY(-10px);
        border-bottom: 10px solid yellow;
        box-shadow: 0 5px 15px rgba(0,0,0,0.2);
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