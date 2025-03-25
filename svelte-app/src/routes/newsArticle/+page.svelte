<div class="overlay"></div>
<div class="header-container">
    <h2>Nosferatu</h2>
    <h3>Spongebobs favourite vampire</h3>
</div>

<div class="body-container">
    <p>
        The new adaptaion of legendary Vampire is set to be an amazing watch. <br>
            The adaptaion of old and classic Nosferatu hit the theaters a while back. We wanted to look at the impact this old school vampire had on audiences. <br>
            Did he pierced the audiances necks or was his frenzy bloodless? Find out more...
    </p>
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

    /* Update the header-container styles */
    .header-container {
        margin-bottom: 2rem;
        
    }
    

    .header-container h2{
        font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 500;
        font-size: 5rem;
        font-style: normal;
        border-bottom: 4px solid yellow;
        text-align: left;
    }

    .header-container h3{
        font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 300;
        font-size: 2rem;
        font-style: nromal;
        text-align: left;
        
    }

	.news-container h3{
		font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 700;
        font-style: normal;
        font-size: 2rem;

        border-bottom: 2px solid yellow;
		
		letter-spacing: 2px;
		text-transform: uppercase;
	}

    .news-container h4{
		font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 500;
        font-style: normal;
        font-size: 1.5rem;
		
		
	}
	
	.news-container p{
		font-family: "Exo 2", sans-serif;
        font-optical-sizing: auto;
        font-weight: 500;
        font-style: normal;
        font-size: 1.25rem;

        
	}
	.news-container > div{
		background-color: rgba(16, 16, 16, 0.6);
		border-radius:30px;
		padding:1.5rem;
	}
    .news-container{
        display: grid;
        grid-template-columns: repeat(1, 1fr); 
        grid-template-rows: auto auto auto;
        gap: 2rem;
		padding:2rem;
        width:80%;
        max-width: 1600px;
        margin:auto;
    }

    .news-article{
        display: grid;
        grid-template-columns: 2fr 2fr;
        gap: 1.5rem;
        border-bottom: 3px solid yellow;
        border-left: 3px solid yellow;
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
	grid-area: 1 / 1 / 1 / 1;
    text-align: left;
	
}

.paragraph{
    grid-area: 2 / 1 / 10 / 3;
    padding: 0 1rem;
    text-align: left;
}

.date {
	grid-area: 2 / 3 / 2 / 3;
    text-align: right;
    border-left: 2px solid rgba(62, 62, 62, 0.3);
    padding-left: 1rem;
}


</style>