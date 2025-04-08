<script>
    // import base to prefix local paths
    import { base } from '$app/paths';
</script>

<div class="overlay"></div>
<div class="page-container">
        <div class="article-content">
            <h1>Fallout</h1>
            <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit,
                sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
                quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor
                in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident,
                sunt in culpa qui officia deserunt mollit anim id est laborum.</p>

            <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit,
                sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
                quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor
                in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident,
                sunt in culpa qui officia deserunt mollit anim id est laborum.</p>

             <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit,
                 sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
                 quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor
                 in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident,
                 sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
        </div>

    <div class="image-grid">
        <div class="image small-image">
            <img src='{base}/fallout.jpg' alt="NCR from Fallout on Prime">
        </div>

        <div class="image small-image">
            <img src='{base}/fallout-s2.png' alt="Leaked NCR Power Armour">
        </div>

        <div class="image large-image">
            <img src='{base}/new-vegas.jpg' alt="Fallout promotional image">
        </div>
    </div>

</div>

<style>
    .image-grid {
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-template-rows: auto auto;
        gap: 1rem;
        width: 100%;
        max-width: 750px;
        margin: 0 auto;
    }

    .small-image {
        grid-column: span 1;
    }

    .large-image {
        grid-column: span 2;
        grid-row: 2;
        max-width: 100%;
    }

    .image {
        background-color: #fff;
        border-radius: 20px;
        overflow: hidden;
        display: flex;
        justify-content: center;
        align-items: center;
        border-bottom: 10px solid var(--articles-color);
        border-left: 10px solid var(--articles-color);
    }
    
    .image img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .small-image img {
        aspect-ratio: 1/1;
    }

    .large-image img {
        aspect-ratio: 16/9;
    }
    
    
    .page-container {
        display: flex;
        flex-direction: row;    
        justify-content: space-between;
        align-items: flex-start;
        padding: 5rem 2rem 2rem;
        min-height: 100vh;
        gap: 2rem;
        max-width: 1400px;
        margin: 0 auto;
        flex-wrap: wrap;
    }

    .article-content {
        padding: 1rem;
        max-width: 800px;
        width: 100%;
        flex: 2; 
        text-align: justify; 
    }
    h1 {
        font-size: 2.5rem;
        margin-bottom: 1.5rem;
        color:white;
        letter-spacing: 2rem;
        border-bottom: 4px solid var(--articles-color);
        text-align: center; 
        width: 100%; 
    }

    p {
        font-family: "Exo 2", sans-serif;
        font-size: 1.2rem;
        color: rgb(255, 255, 255);
        line-height: 1.6;
        margin-bottom: 1.5rem; 
    }
    @media (max-width: 850px) {
        .page-container {
            flex-direction: column;
            align-items: center;
            padding: 3rem 1rem 1rem; 
        }
        
        .article-content {
            max-width: 100%;
            padding: 1rem;
            text-align: left; 
        }
        
        .image-grid {
            width: 95%;
            grid-template-columns: 1fr;
            gap: 1rem;
        }
        
        .small-image, .large-image {
            grid-column: span 1;
            margin-top: 1rem;
        }
        
        h1 {
            font-size: 2rem;
            letter-spacing: 1rem; 
        }
    }

    @media (min-width: 851px) and (max-width: 1200px) {
        .image-grid {
            max-width: 650px;
        }
    }
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
</style>