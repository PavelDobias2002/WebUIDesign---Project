<script>
    import { scale } from 'svelte/transition';
</script>

<div class="page-container">
    <div class="article-container">
        <div class="article-content">
            <!-- Your article content goes here -->
            <h1>Article Fallout</h1>
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
</div>

<style>
        .container {
        position: relative;
        max-width: 1000px;
        margin: 100px auto;
        padding: 0 20px;
    }

    .overlap-image {
        position: absolute;
        bottom: -30px;
        left: -30px;
        width: 200px;
        height: 200px;
        object-fit: cover;
        border-radius: 15px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        z-index: 2;
    }
    .page-container {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        padding: 1rem;
        min-height: 100vh;
    }

    .article-container {
        background-color: #fff;
        border-radius: 20px;
        overflow: hidden;
        max-width: 1500px;
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
        .article-container {
            max-width: 95%;
        }
        
        .article-content {
            padding: 1.5rem;
        }
    }
</style>