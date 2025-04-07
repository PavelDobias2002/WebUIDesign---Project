<div class="overlay"></div> <!--Overlay over the page background creating subtle gradient-->
<div class="header-container"> <!--Header with titles-->
    <h2>Nosferatu</h2>
    <h3>Spongebobs favourite vampire</h3>
</div>

<div class="body-container"> <!--Contaier of the news article body-->
    
    <p class="paragraph">
        The new adaptaion of legendary Vampire is set to be an amazing watch. <br>
            The adaptaion of old and classic Nosferatu hit the theaters a while back. We wanted to look at the impact this old school vampire had on audiences. <br>
            Did he pierced the audiances necks or was his frenzy bloodless? Find out more about the impact Nosferatu had on our childhoods.
    </p>

    <img class="image" src='/nosferatu.png' alt="image of nosferatu from Spongebob episode">

    <p class="paragraph2">
        The Nosferatu frenzy took to the streets and we had to ask the fans what they think, in our Nosferatu Review we took the nostalgia as a factor in people perception of this movie. <br>
        Our team thinks this is a news worthy topic, shaping the brains of children to have this imprinted version of Nosferatu iconic design. The author thanked himself to the creator of Spongebob for making Nosferatu into cult classic.
    </p>

    <h2 class="title">
        Horror as a children favourite genre?
    </h2>
    
    <p class="paragraph3">
        It has been shown that younger kids enjoy horror, and a children horror books has been a popular trend for few years now. Even the Warhammer universe, arguably one of the most depressing ones out there, has quite good children books. <br>

    </p>

    <img class ="image2" src='/nigthmare.jpg' alt="image of nightmare before christmass movie">  

    <p class="paragraph4">
        We can go back as legendary as Tim Burtons The Nightamere Before Christmass, a movie targeting kids with its whipsicl animation and art style. But as many know having horror themes and adult centeret content. While marketed as a family-friendly film, The Nightmare Before Christmas incorporates various horror elements that might not be immediately apparent to young viewers.

        Even the film’s musical numbers, composed by Danny Elfman, carry eerie undertones. Songs like “This Is Halloween” celebrate the thrills of fright, while “Oogie Boogie’s Song” introduces a sadistic gambling villain. These moments contribute to the film’s spooky atmosphere while still remaining accessible to children.
    </p>

    <h2 class="title2">
        Other News
    </h2>

    <nav class="news-nav">
        <ul>
            <li><a href="/newsArticle">Writers Strike</a></li>
            <li><a href="/newsArticle">Writers Strike</a></li>
            <li><a href="/newsArticle">Writers Strike</a></li>
            <li><a href="/newsArticle">Writers Strike</a></li>
            <li><a href="/newsArticle">Writers Strike</a></li>
        </ul>
    </nav>

</div>


<style>
.overlay 
{ /*the gradient on the page background*/
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
.header-container 
{
    margin-bottom: 2rem;
    padding-top: 10%;
    width: 75%;
    max-width: 1600px;
    margin: auto;
}
.body-container p
{
	font-family: "Exo 2", sans-serif;
    font-optical-sizing: auto;
    font-weight: 500;
    font-style: normal;
    font-size: 1.25rem;
    text-align: left;
}

.header-container h2
{
    font-family: "Exo 2", sans-serif;
    font-optical-sizing: auto;
    font-weight: 500;
    font-size: 5rem;
    font-style: normal;
    border-bottom: 4px solid var(--news-color);
    text-align: left;
}

.header-container h3
{
    font-family: "Exo 2", sans-serif;
    font-optical-sizing: auto;
    font-weight: 300;
    font-size: 2rem;
    font-style: nromal;
    text-align: left;
}

.body-container h2
{
	font-family: "Exo 2", sans-serif;
    font-optical-sizing: auto;
    font-weight: 700;
    font-style: normal;
    font-size: 1.5rem;

    border-bottom: 2px solid var(--news-color);
		
	letter-spacing: 2px;
}

.body-container
{
    display: grid;
    grid-template-columns: repeat(2, 1fr); 
    grid-template-rows: repeat(1, 1fr);
    gap: 1rem;
    width:75%;
    max-width: 1600px;
    margin:auto;
}

.image, .image2 
{
    width: 100%;
    height: auto;
    object-fit: cover;
    border-radius: 8px;
}

/*Image layout desktop*/
.image 
{
	grid-area: 1 / 2 / 2/ 2; /*row start column start/row end column end*/
}

.image2{
    grid-area: 5 / 1/ 5/ 1;
}

/*text positioning using grid*/

.title 
{
	grid-area: 4 / 1 / 3 / 3;
    text-align: left;
	
}

.title2 
{
	grid-area: 6 / 1 / 6 / 3;
    text-align: left;
	
}

.paragraph
{
    grid-area: 1 / 1 / 1 / 1;
    text-align: left;
}

.paragraph2
{
    grid-area: 2 / 1 / 2 / 3
}

.paragraph3
{
    grid-area: 4 / 1 / 4 / 3
}

/*navigation positioning*/

.news-nav
{
    display: flex;
    text-align: left;
    grid-area: 7 / 1 / 7 / 3
}

.news-nav ul
{
    display: flex;
    gap: 1rem;
    text-align: left;
    flex-wrap: wrap;
}

.news-nav ul li
{
    list-style-type: none;
    padding: 0.5rem;
    border-left: 2px solid var(--news-color);
    text-align: center;
}

.news-nav ul li:hover
{
    transform: scale(1.050);
}

/* Tablet breakpoint (max-width: 1024px) */
@media screen and (max-width: 64em) {
    .body-container,
    .header-container {
        width: 85%;
    }

    .header-container h2 {
        font-size: 4rem;
    }

    .header-container h3 {
        font-size: 1.75rem;
    }

    .body-container p {
        font-size: 1.1rem;
    }

    .news-nav ul {
        gap: 0.75rem;
    }
}

/* Mobile breakpoint (max-width: 768px) */
@media screen and (max-width: 48em) {
    .body-container,
    .header-container {
        width: 95%;
    }

    .body-container {
        grid-template-columns: 1fr; /*go for one column for mobiles*/
        gap: 1.5rem;
    }

    /* Reposition grid items for mobile D:*/
    .image {
        grid-area: 2 / 1 / 3 / 2;
    }

    .paragraph {
        grid-area: 1 / 1 / 2 / 2;
    }

    .paragraph2 {
        grid-area: 3 / 1 / 4 / 2;
    }

    .title {
        grid-area: 4 / 1 / 5 / 2;
    }

    .paragraph3 {
        grid-area: 5 / 1 / 6 / 2;
    }

    .image2 {
        grid-area: 6 / 1 / 7 / 2;
    }

    .paragraph4 {
        grid-area: 7 / 1 / 8 / 2;
    }

    .title2 {
        grid-area: 8 / 1 / 9 / 2;
    }

    .news-nav {
        grid-area: 9 / 1 / 10 / 2;
    }

    /* Header styles for mobile */
    .header-container h2 {
        font-size: 3rem;
    }

    .header-container h3 {
        font-size: 1.5rem;
    }

    /* Navigation styles for mobile */
    .news-nav ul {
        flex-direction: column;
        gap: 0.5rem;
        width: 100%;
    }

    .news-nav ul li {
        width: 100%;
        border-left: none;
        border-bottom: 2px solid var(--news-color);
    }
}

</style>