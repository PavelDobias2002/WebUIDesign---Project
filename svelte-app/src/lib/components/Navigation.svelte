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
          :root {
        --logo-scale: 0.35;
        --logo-top-position: -27%;
        --nav-gap: 4rem;
        --nav-margin: 4rem;
        --nav-item-margin: 0 25px;
    }
    .nav {
        z-index: 100;
        position: fixed;
        width:100%;
        padding-top: 100px;
        margin:auto;
    
    }
    .nav::before {
        content: '';
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translateX(-50%);
        width: calc(100% - 7rem); /* Matches the ul width (accounting for margins) */
        height: calc(100% - 80px); /* Accounts for padding-top */
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
        margin-left: var(--nav-margin);
        margin-right: var(--nav-margin);
        gap: var(--nav-gap);
        display: flex;
        background-color: rgb(0, 0, 0);
        border-radius: 50px;
        justify-content: center;
        align-items: center;
    }
    
    .nav ul li {
        margin: var(--nav-item-margin);
    }
    
    .nav ul li a {
        font-family: 'Pixelify Sans';
        font-size: large;
        text-decoration: none;
        color: rgb(255, 255, 255);
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
        color: var(--news-color);
    }
    .link-news::after {
        background-color: var(--news-color);
    }
    
    
    .link-articles::before {
        color: var(--articles-color);
    }
    .link-articles::after {
        background-color:var(--articles-color);
    }
    
    
    .link-reviews::before {
        color: var(--reviews-color);
    }
    .link-reviews::after {
        background-color: var(--reviews-color);
    }
    
    
    .link-about::before {
        color: var(--about-color);
    }
    .link-about::after {
        background-color:var(--about-color);
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
        position:absolute;
        left: 50%;
        transform: translateX(-50%) scale(var(--logo-scale));
        top: var(--logo-top-position);
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
      50% { transform: rotate(0deg); }
      75% { transform: rotate(-5deg); }
      100% { transform: rotate(0deg); }
    }
    
    .burger {
        display: none;
        background: none;
        border: none;
        font-size: 2rem;
        color: white;
        cursor: pointer;
        z-index: 200;
        padding: 10px 15px;
        border-radius: 5px;
        transition: all 0.3s ease;
        position: absolute;
        right: 20px;
        top: 20px;
    }
    
    .burger:hover {
        transform: scale(1.1);
        background-color: rgba(255, 255, 255, 0.1);
    }
    
    /* Mobile Navigation: Show Burger Menu */
    @media (max-width: 768px) {
        .nav {
            padding-top: 10px;
            width:100vw;
        }
        
        .burger {
            display: block;
            top:-10%;
        }
        
        .nav ul {
            display: none;
            flex-direction: column;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100vh;
            text-align: center;
            padding: 80px 0 30px 0;
            background-color: rgba(0, 0, 0, 0.95);
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            transform: translateY(-100%);
            transition: transform 0.5s ease, opacity 0.3s ease;
            opacity: 0;
            z-index: 99;
            border-radius: 0;
            margin: 0;
            justify-content: center;
            gap: 2rem;
        }
        
        .nav ul.open {
            display: flex;
            transform: translateY(0);
            opacity: 1;
        }
        
        .nav ul::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, #ff0000, #ff7300, #fffb00, #48ff00, #00ffd5, #002bff, #7a00ff, #ff00c8, #ff0000);
            background-size: 400%;
            filter: blur(15px);
            opacity: 0.15;
            animation: animateGlow 20s linear infinite;
            z-index: -1;
        }
        
        .nav ul li {
            padding: 15px 0;
            margin: 5px 0;
            width: 100%;
        }
        
        .nav ul li a {
            font-size: 1.2rem;
            display: inline-block;
            padding: 10px 0;
            width: auto;
            position: relative;
        }
        
        .nav ul li a:hover {
            transform: scale(1.2);
        }
        
        .home-logo {
            gap:15px;
            top:25px;
            transform: translateX(-55%) translateY(-50%) scale(0.45); /* Center*/
            margin-bottom:2rem;
            z-index:200;
            box-shadow: 0 5px 50px rgba(255, 255, 255, 0.3);
        }
        
        /* Hide spacers on mobile */
        .logo-spacer, .logo-spacer2 {
            display: none;
        }
    }
        /*tablet*/
        @media (min-width: 769px) and (max-width: 1024px) {
            /* Fixed values for consistent tablet view */
            .nav {
                padding-top: 80px; /* Adjusted to accommodate logo */
            }
            
            .nav ul {
                max-width: 90%;
                margin: 0 auto; /* Center the navigation bar */
                gap: 2rem;
                padding: 0.8rem 1.5rem;
            }
            
            .nav ul li a {
                font-size: medium;
            }
            
            /* Center the gradient background */
            .nav::before {
                top: 75%; /* Align with content */
                width: calc(100% - 5rem);
                height: 75px; /* Fixed height for stability */
                transform: translateX(-50%) translateY(-50%); /* Center*/
            }
            
            /* Fixed logo positioning for tablets */
            .home-logo {
                position: absolute;
                left: 50%;
                height:90%;
                top: calc(100% - 8rem);
                transform: translateX(-50%) scale(0.3);
                z-index: 101; /* Ensure logo stays on top */
            }
            
            /* Adjust logo spacers for better spacing */
            .logo-spacer, .logo-spacer2 {
                width: 80px; /* Create space for centered logo */
            }
        }
    </style>
    
     
    