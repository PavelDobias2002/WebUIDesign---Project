<script>
    import { onMount } from 'svelte';
    import { Card } from '$lib';
    import { Card2 } from '$lib';
    
    let cardContainer;
    let cards = [];

    let movieContainer;
    let movies = [];
    
    // Track if the suggestion button is expanded
    let isExpanded = false;
    
    // Function to toggle expansion state
    function toggleExpand() {
        isExpanded = !isExpanded;
    }
    
    // Track if the suggestion button is expanded
    let isExpanded = false;
    
    // Function to toggle expansion state
    function toggleExpand() {
        isExpanded = !isExpanded;
    }
<div class="suggest-content-container">
    <div class="suggest-button" class:expanded={isExpanded}>
        <button type="button" on:click={toggleExpand}>
            Suggest us new content!
            <span class="arrow-icon">{isExpanded ? '▲' : '▼'}</span>
        </button>
        <div class="expanded-content" class:visible={isExpanded}>
            <p>Have ideas for articles, reviews, or news stories you'd like to see on our site? 
            Let us know what content you're interested in, and our team will consider your suggestions for future publications!</p>
        </div>
    </div>
</div>
    .suggest-content-container {
        position: relative;
        z-index: 10;
        margin-top: 120px;
        width: 100%;
        display: flex;
        justify-content: center;
    }

    .suggest-button{
        position: relative;
        z-index: 10;
        display: inline-block;
        transition: transform 0.3s ease-out, width 0.4s ease-in-out, height 0.4s ease-in-out;
        max-width: 500px;
        width: 80%;
    }

    .suggest-button.expanded {
        transform: translateY(0);
        width: 80%;
        max-width: 700px;
    }

    .suggest-button button{
        position: relative;
        padding: 22px 48px;
        width: 100%;
        border: none;
        border-radius: 12px;
        font-family: 'Pixelify Sans', sans-serif;
        font-size: 1.2rem;
        font-weight: bold;
        letter-spacing: 1px;
        text-align: center; 
        box-shadow: 0 5px 20px rgba(255, 255, 255, 0.3);
        background: linear-gradient(135deg, #4a00e0, #8e2de2);
        color: white;
        transition: all 0.4s ease;
        cursor: pointer;
        overflow: hidden;
        border-bottom-left-radius: 12px;
        border-bottom-right-radius: 12px;
    }

    .suggest-button.expanded button {
        border-bottom-left-radius: 0;
        border-bottom-right-radius: 0;
    }

    .arrow-icon {
        display: inline-block;
        margin-left: 10px;
        transition: transform 0.3s ease;
    }

    .expanded-content {
        max-height: 0;
        overflow: hidden;
        background-color: rgba(255, 255, 255, 0.9);
        color: #333;
        border-bottom-left-radius: 12px;
        border-bottom-right-radius: 12px;
        transition: max-height 0.4s ease-in-out, padding 0.4s ease;
        padding: 0 20px;
        box-shadow: 0 5px 20px rgba(255, 255, 255, 0.3);
    }

    .expanded-content.visible {
        max-height: 300px;
        padding: 20px;
    }

    .expanded-content p {
        margin: 0;
        color: #333;
        line-height: 1.6;
    }
<div class="suggest-content-container">
    <div class="suggest-button" class:expanded={isExpanded}>
        <button type="button" on:click={toggleExpand}>
            Suggest us new content!
            <span class="arrow-icon">{isExpanded ? '▲' : '▼'}</span>
        </button>
        <div class="expanded-content" class:visible={isExpanded}>
            <p>Have ideas for articles, reviews, or news stories you'd like to see on our site? 
            Let us know what content you're interested in, and our team will consider your suggestions for future publications!</p>
        </div>
    </div>
</div>
    .suggest-content-container {
        position: relative;
        z-index: 10;
        margin-top: 120px;
        width: 100%;
        display: flex;
        justify-content: center;
    }

    .suggest-button{
        position: relative;
        z-index: 10;
        display: inline-block;
        transition: transform 0.3s ease-out, width 0.4s ease-in-out, height 0.4s ease-in-out;
        max-width: 500px;
        width: 80%;
    }

    .suggest-button.expanded {
        transform: translateY(0);
        width: 80%;
        max-width: 700px;
    }

    .suggest-button button{
        position: relative;
        padding: 22px 48px;
        width: 100%;
        border: none;
        border-radius: 12px;
        font-family: 'Pixelify Sans', sans-serif;
        font-size: 1.2rem;
        font-weight: bold;
        letter-spacing: 1px;
        text-align: center; 
        box-shadow: 0 5px 20px rgba(255, 255, 255, 0.3);
        background: linear-gradient(135deg, #4a00e0, #8e2de2);
        color: white;
        transition: all 0.4s ease;
        cursor: pointer;
        overflow: hidden;
        border-bottom-left-radius: 12px;
        border-bottom-right-radius: 12px;
    }
    
    .suggest-button.expanded button {
        border-bottom-left-radius: 0;
        border-bottom-right-radius: 0;
    }
    
    .arrow-icon {
        display: inline-block;
        margin-left: 10px;
        transition: transform 0.3s ease;
    }
    
    .expanded-content {
        max-height: 0;
        overflow: hidden;
        background-color: rgba(255, 255, 255, 0.9);
        color: #333;
        border-bottom-left-radius: 12px;
        border-bottom-right-radius: 12px;
        transition: max-height 0.4s ease-in-out, padding 0.4s ease;
        padding: 0 20px;
        box-shadow: 0 5px 20px rgba(255, 255, 255, 0.3);
    }
    
    .expanded-content.visible {
        max-height: 300px;
        padding: 20px;
    }
    
    .expanded-content p {
        margin: 0;
        color: #333;
        line-height: 1.6;
    }
    
    .suggest-button button:before {
        content: '';
        position: absolute;
        top: 0;
        left: -100%;
        width: 100%;
        height: 100%;
        background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
        transition: 0.5s;
    }
    
    .suggest-button:hover {
        transform: translateY(-5px);
    }
    
    .suggest-button button:hover {
        box-shadow: 0 8px 25px rgba(142, 45, 226, 0.6);
        transform: scale(1.05);
        background: linear-gradient(135deg, #8e2de2, #4a00e0);
    }
    
    .suggest-button button:hover:before {
        left: 100%;
        animation: shine 1.5s infinite;
    }
    
    @keyframes shine {
        0% {
            left: -100%;
        }
        100% {
            left: 100%;
        }
    }
