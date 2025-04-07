<script>
    import { scale } from 'svelte/transition';
</script>

<div class="page-container">
    <div class="article-container">
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
    </div>

    <div class="image">
        <img src='/fallout.jpg' alt="Bridget Jones movie poster">
    </div>

    <div class="image2">
        <img src='/fallout-s2.png' alt="Bridget Jones movie poster">
    </div>

</div>

<style>

    .image {
        background-color: #fff;
        border-radius: 20px;
        overflow: hidden;
        display: flex;
        justify-content: center;
        align-items: center;
        flex: 1;
        max-width: 450px;
        border-bottom: 10px solid var(--articles-color);
        border-left: 10px solid var(--articles-color);
        box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
    }
    
    .image img {
        width: 100%;
        height: 100%;
        aspect-ratio: 1/1;
        object-fit: cover;
    }

    .image2 {
        background-color: #fff;
        border-radius: 20px;
        overflow: hidden;
        display: flex;
        justify-content: center;
        align-items: center;
        flex: 1;
        max-width: 450px;
        border-bottom: 10px solid var(--articles-color);
        border-left: 10px solid var(--articles-color);
        box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
    }
    
    .image2 img {   
        width: 100%;
        height: 100%;
        aspect-ratio: 1/1;
        object-fit: cover;
    }
    
    
    .page-container {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: flex-start;
        padding: 2rem;
        min-height: 100vh;
        gap: 2rem;
        max-width: 1400px;
        margin: 0 auto;
    }

    .article-container {
        background-color: #fff;
        border-radius: 20px;
        overflow: hidden;
        flex: 2;
        max-width: 800px;
        width: 100%;
        border-bottom: 10px solid var(--articles-color);
        border-left: 10px solid var(--articles-color);
        box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
    }


        .article-content {
            padding: 2rem;
        }

    h1 {
        font-size: 2.5rem;
        margin-bottom: 1.5rem;
        color: black;
    }

    p {
        font-family: "Exo 2", sans-serif;
        font-size: 1.2rem;
        color: rgb(75, 75, 75);
        line-height: 1.6;
    }

    @media (max-width: 850px) {
        .page-container {
            flex-direction: column;
            align-items: center;
        }
        
        .article-container {
            max-width: 95%;
        }
        
        .image {
            max-width: 95%;
            margin-top: 2rem;
        }
        
        .article-content {
            padding: 1.5rem;
        }
    }
</style>