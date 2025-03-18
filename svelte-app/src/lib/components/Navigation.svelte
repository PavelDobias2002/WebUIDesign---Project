<script>
let isOpen = false; // Menu state (open/closed)
</script>

<nav class="nav">
    <!-- Burger Menu Button (Visible on Small Screens) -->
<button class="burger" on:click={( ) => isOpen = ! isOpen} aria-label="Toggle navigation"> ☰ 
</button>

<ul class : open={isOpen}>
        <li><a href="/news">News</a></li>
        <li><a href="/articles">Articles</a></li>
        <li><a href="/">Home</a></li>
        <li><a href="/reviews">Reviews</a></li>
        <li><a href="/about">About</a></li>
    </ul>
</nav>

<style>
.nav ul {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    justify-content: center;
}

.nav ul li {
    margin: 0 25px;
}

.nav ul li a {
    font-family: 'Pixelify Sans';
    font-size: large;
    text-decoration: none;
    color: white;
    font-weight: bold;
}



/* Mobile Navigation: Show Burger Menu */
@media (max-width: 768px) {
.burger {
    display: block; /* Show burger icon */
    left: 90%;
}

.nav ul {
    display: none; /* Hide menu by default */
    flex-direction: column;
    position: absolute;
    top: 90px;
    left: 0;
    width:100%;
    text-align:left;
    padding: 0 1rem;
    background: #007bff;
    box-shadow: 0 4px 6px rgba(0,0,0,0.1);
}

.nav ul.open{
    display:flex;
}

.nav ul li{
    padding: 20px 20px;
}
}
</style>

 
