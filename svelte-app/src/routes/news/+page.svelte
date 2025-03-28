<script>

</script>
<div class="overlay"></div> <!--Overlay over the page background creating subtle gradient-->
<div class="header-container">  <!--Header with titles-->
    <h1>News News and more News!</h1>
    <h2>From Cinema to your screen.</h2>
</div>

<div class="news-container">    <!--Container containing all the news articles-->
	
    <div class="news-article">  <!--div for each article -->
        
        <div class="title"> <!--Left side of the div with titles-->
		    <a href="/newsArticle">
            <h3>Nosferatu</h3>
            <h4>Spongebobs favourite vampire</h4>
            </a>
	    </div>
	    
        <div class="paragraph"> <!--Middle section for description of the news-->
            <a href="/newsArticle">
            <p>The new adaptaion of legendary Vampire is set to be an amazing watch. <br>
            The adaptaion of old and classic Nosferatu hit the theaters a while back. We wanted to look at the impact this old school vampire had on audiences. <br>
            Did he pierced the audiances necks or was his frenzy bloodless? Find out more...</p>
            </a>
        </div>

        <div class="date">  <!-- date and editor info on the right -->
		    <h3>Date:</h3>
		    <p>25/03/2025</p>
            <h3>Editor:</h3>
            <p>Pavel Dobias</p>
	    </div>
    </div>

    <!-- This layout is used for each news article div-->

    <div class="news-article">

	    <div class="title">
		    
            <h3>Writers Strike!</h3>
            <h4>Another dent in Hollywoods trails</h4>
            
	    </div>
	    
        <div class="paragraph">
            <p>After the cuts, writers hit the streets and...</p>

        </div>

        <div class="date">
		    <h3>Date:</h3>
		    <p>25/03/2025</p>
            <h3>Editor:</h3>
            <p>Pavel Dobias</p>
	    </div>
        
        <div class="container">

        </div>
    </div>
    
    <div class="news-article">

	    <div class="title">
            <a href="/about">
		    <h3>Mickey 17</h3>
            <h4>Weird movie</h4>
            </a>
	    </div>
	    
        <div class="paragraph">
            <p>​Bong Joon Ho's latest film, "Mickey 17," is a sci-fi satire starring Robert Pattinson as Mickey Barnes, an expendable crew member on a space colonization mission. In this dystopian future, Earth is plagued by environmental disasters, prompting a mission to colonize Niflheim. Mickey's role involves repeated dangerous tasks, resulting in his death and subsequent reprinting with retained memories.</p>

        </div>

        <div class="date">
		    <h3>Date:</h3>
		    <p>25/03/2025</p>
            <h3>Editor:</h3>
            <p>Pavel Dobias</p>
	    </div>
        
        <div class="container">

        </div>
    </div>

    <div class="news-article">
	    <div class="title">
		    <h3>Minecraft Flop?</h3>
            <h4>The movie adaptation of beloved game causing waves.</h4>
	    </div>
	    
        <div class="paragraph">
            <p>
                The first trailer of upcoming Minecraft Movie left a fans of the series questing the decisions made by the studio.<br>
                The backlog of amazing Minecraft animations makes the fans to come to one conclussion: "Why isnt the movie animated?"<br>
                Find out more...
            </p>

        </div>

        <div class="date">
		    <h3>Date:</h3>
		    <p>25/03/2025</p>
            <h3>Editor:</h3>
            <p>Pavel Dobias</p>
	    </div>
        
        <div class="container">

        </div>
    </div>

    
	
</div>



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
        -webkit-text-stroke: 2px yellow;
        color: transparent;
        transition: transform 0.3s ease;
        animation: strokeTransition 2s ease-in-out infinite alternate;
    }

    

    .header-container h2{ /*style for sub heading*/
        font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 500;
        font-size: 5rem;
        font-style: normal;
        border-bottom: 4px solid yellow;
    }

	.news-container h3{ /*Style for heading within the news article divs*/
		font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 700;
        font-style: normal;
        font-size: 2rem;

        border-bottom: 2px solid yellow;
		
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
        border-bottom: 3px solid yellow;
        border-left: 3px solid yellow;
        transition: all 0.3s ease;
    }

    .news-article:hover {   /*When hover on the article it goes up to emphasize clickability*/
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

.container{
    grid-area: 1 / 1 / 1 / 3;
    z-index: -1;
}

</style>