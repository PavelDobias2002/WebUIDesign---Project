<script>
    import { onMount } from 'svelte';
	import { scale } from 'svelte/transition';
    
    onMount(() => {
        console.log("about page loaded");
    });
</script>

<!DOCTYPE html>

<html lang="en">
<head>
    
    <title>thumbnail grid</title>
    <style>
        h1 {
            text-align: center;
            color: white;
            font-size: 120px;
            text-shadow: 0 0 15px rgba(255, 255, 255, 0.3);
            transition: text-shadow 0.3s ease, transform 0.3s ease;
        }

        .article-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(400px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .article-card {
            background-color: #fff;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }

        .article-card:hover {
            transform: translateY(-5px);
        }

        .article-image {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .article-content {
            padding: 10px;
        }

        .article-title {
            font-size: 175%  ;
            margin-bottom: 0.75rem;
            color: black;
        }

        .article-description {
            color: grey;
            font-size: 125%;
            margin-bottom: 1rem;
        }

        .article-link {
            display: inline-block;
            color: #3498db;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.2s ease;
        }

        
        .article-link:hover {
            animation: shaky 0.2s ease;
            color: #2980b9;
            scale: 1.5;
            transition: all 300ms ease-in-out;
            text-decoration: underline;
        }
        
        @keyframes shaky {
            0% { transform: rotate(0deg); }
            25% { transform: rotate(5deg); }
            50% { transform: rotate(0deg); }
            75% { transform: rotate(-5deg); }
            100% { transform: rotate(0deg); }
        }

        .reveal-text {
            opacity: 0;
            transform: translateY(20px);
            animation: revealText 1s forwards ease-out;
        }

        h1:hover {
            text-shadow: 0 0 25px rgba(255, 255, 255, 0.5);
            transform: scale(1.02)
        }

        @keyframes revealText {
            0% {
                opacity: 0;
                transform: translateY(20px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

    </style>
</head>
<body>
    <h1 class="reveal-text">Latest Articles</h1>
    
    <div class="article-grid">
        <!-- article 1 :) -->
        <div class="article-card">
            <img src="placeholder.jpg" alt="thumbnail" class="article-image">
            <div class="article-content">
                <h2 class="article-title">Why No signal is the greatest</h2>
                <p class="article-description">blah blah blah</p>
                <a href="#" class="article-link">Read More ☺ </a>
            </div>
        </div>

        <!-- article 2 -->
        <div class="article-card">
            <img src="placeholder.jpg" alt="thumbnail" class="article-image">
            <div class="article-content">
                <h2 class="article-title">Why No signal is the greatest</h2>
                <p class="article-description">blah blah blah</p>
                <a href="#" class="article-link">Read More ☺ </a>
            </div>
        </div>

        <!-- article 3 -->
        <div class="article-card">
            <img src="placeholder.jpg" alt="thumbnail" class="article-image">
            <div class="article-content">
                <h2 class="article-title">Why No signal is the greatest</h2>
                <p class="article-description">blah blah blah</p>
                <a href="#" class="article-link">Read More ☺ </a>
            </div>
        </div>
    </div>
</body>
</html>