<script>
    export let title = "article title";
    export let description = "Article description";
    export let image = "";
    export let link = "#";
</script>
<div class="article-card" transition:scale >
    <img src={image} alt={title} class="article-image">
    <div class="article-content">
        <h2 class="article-title">{title}</h2>
        <p class="article-description">{description}</p>
        <a href={link} class="article-link">Read More!</a>
    </div>
</div>

<style>
    .article-card {
        background-color: #fff;
        border-radius: 20px;
        overflow: hidden;
        transition: transform 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275), box-shadow 0.4s ease, border-bottom 0.3s ease, border-left 0.3s ease;
        position: relative;
        transform-origin: center;
        border-bottom: 10px solid var(--articles-color);
        border-left: 10px solid var(--articles-color);
    }

    .article-card:hover {
        transform: translateY(-10px) scale(1.01);
        box-shadow: 0 12px 24px rgba(0, 0, 0, 0.15), 0 5px 15px rgba(46, 235, 219, 0.2);
        border-bottom: 20px solid var(--articles-color);
        margin-top: 5px;
    }

    .article-image {
        width: 100%;
        aspect-ratio: 16/9;
        object-fit: cover;
        transition: transform 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        display: block;
    }

    .article-card:hover .article-image {
        transform: scale(1.05);
    }

    .article-content {
        padding: 20px;
        transition: padding 0.2s ease;
    }

    .article-card:hover .article-content {
        padding: 18px 15px;
    }

    .article-title {
        font-size: 200%;
        margin-bottom: 0.75rem;
        color: black;
    }

    .article-description {
        font-family: "Exo 2", sans-serif;
        font-size: 135%;
        color: rgb(75, 75, 75);
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
        font-size: 30px;
        animation: shaky 0.2s ease;
        color: var(--articles-color);
        transition: all 200ms ease-in-out;
        text-decoration: underline;
    }

    @keyframes shaky {
        0% { transform: rotate(0deg); }
        25% { transform: rotate(5deg); }
        50% { transform: rotate(0deg); }
        75% { transform: rotate(-5deg); }
        100% { transform: rotate(0deg); }
    }
</style>