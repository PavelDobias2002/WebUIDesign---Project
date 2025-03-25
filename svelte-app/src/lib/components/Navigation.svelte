<script>
    let isOpen = false; // Menu state (open/closed)
    </script>
    
    <nav class="nav">
        <button class="burger" on:click={() => isOpen = !isOpen} aria-label="Toggle navigation">
            ≡
        </button>
    
        <div class="home-logo">
            <li><a href="/"><img src="/logo.png" alt="Website Logo"></a></li>
        </div>
    
        <ul class:open={isOpen}>
            <li><a href="/news" data-text="News" class="link-news">News</a></li>
            <li><a href="/articles" data-text="Articles" class="link-articles">Articles</a></li>
            <li class="logo-spacer"></li>
            <li class="logo-spacer2"></li>
            <li><a href="/reviews" data-text="Reviews" class="link-reviews">Reviews</a></li>
            <li><a href="/about" data-text="About" class="link-about">About</a></li>
        </ul>
    </nav>
    
    <style>
    .nav {
        z-index: 2;
        position: relative;
        width:100%;
        padding-top: 20px;
        margin:auto;
    
    }
    .nav::before {
        content: '';
        position: absolute;
        top: 12%;
        left: 50%;
        transform: translateX(-50%);
        width: calc(100% - 7rem); /* Matches the ul width (accounting for margins) */
        height: calc(100% - 10px); /* Accounts for padding-top */
        background: linear-gradient(45deg, #ff0000, #ff7300, #fffb00, #48ff00, #00ffd5, #002bff, #7a00ff, #ff00c8, #ff0000);
        background-size: 400%;
        border-radius: 50px; /* Matches nav border-radius */
        filter: blur(8px); /* Softens the gradient effect */
        opacity: 0.8; /* Slight opacity to blend nicely */
        animation: animateGlow 20s linear infinite;
        z-index: -1; /* Place the gradient behind the nav */
    }
    
    @keyframes animateGlow {
        0% {
            background-position: 0% 50%;
        }
        25% {
            background-position: 100% 50%;
        }
        50% {
            background-position: 100% 100%;
        }
        75% {
            background-position: 0% 100%;
        }
        100% {
            background-position: 0% 50%;
        }
    }
    .nav ul {
        list-style: none;
        padding: 1rem;
        margin-left: 4rem;
        margin-right: 4rem;
        gap: 4rem;
        display: flex;
        background-color: black;
        border-radius: 50px;
        justify-content: center;
        align-items: center;
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
        display:inline-block;
        position:relative;
         transition: all 0.3s ease;
    }
    .nav ul li a::before {
        content: attr(data-text);
        position: absolute;
        overflow:hidden;
        left:0;
        width:0;
        white-space: nowrap;
        transition:all 0.5s;
    }
    nav ul li a::after{
        content: "";
            display: block;
            width: 40%;
            height: 2px;
            border-radius: 50px;
            margin: 0 auto 10px auto;
            transition: width 0.3s ease-in-out;
    }
    /*evry link has its own color*/
    .link-news::before {
        color: #f9f225;
    }
    .link-news::after {
        background-color: #f9f225;
    }
    
    
    .link-articles::before {
        color: #2eebdb;
    }
    .link-articles::after {
        background-color: #2eebdb;
    }
    
    
    .link-reviews::before {
        color: #f31313;
    }
    .link-reviews::after {
        background-color: #f31313;
    }
    
    
    .link-about::before {
        color: #3c1af8;
    }
    .link-about::after {
        background-color: #3c1af8;
    }
    
    
    .nav ul li a:hover{
        transform:scale(1.4);
    }
    .nav ul li a:hover::after{
        width:100%;
    }
    .nav ul li a:hover::before {
        width: 100%;
    }
    
    .home-logo {
        position: absolute;
        left: 50%;
        transform: translateX(-50%) scale(0.35);
        top:-150%;
        z-index: 2;
    }
    
    /* Hide the list item that contains the logo to maintain spacing */
    .home-logo li {
        visibility: hidden;
    }
    
    /* But show the actual logo */
    .home-logo li a {
        visibility: visible;
    }
    .home-logo li:hover{
        animation: shaky 0.2s linear;
    }
    
    @keyframes shaky {
      0% { transform: rotate(0deg); }
      25% { transform: rotate(5deg); }
      50% { transform: rotate(0eg); }
      75% { transform: rotate(-5deg); }
      100% { transform: rotate(0deg); }
    }
    
    .burger {
        display: none;
    }
    
    /* Mobile Navigation: Show Burger Menu */
    @media (max-width: 768px) {
        .burger {
            display: block;
            left: 90%;
        }
    
        .nav ul {
            display: none;
            flex-direction: column;
            position: absolute;
            top: 90px;
            left: 0;
            width: 100%;
            text-align: left;
            padding: 0 1rem;
            background: #007bff;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
    
        .nav ul.open {
            display: flex;
        }
    
        .nav ul li {
            padding: 20px 20px;
        }
    
        .home-logo {
            position: absolute;
            top: -20px;
            transform: translateX(-50%) scale(0.25);
        }
    
    
    }
    </style>
    
     
    