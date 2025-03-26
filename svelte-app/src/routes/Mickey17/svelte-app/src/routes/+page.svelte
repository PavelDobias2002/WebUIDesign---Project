18|    }
</script>
</div>

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
<style>
    .content {
        position: relative;
        z-index: 3;
        padding: 4rem 2rem;
        max-width: 1200px;
        margin: 0 auto;
        height: 100vh;
        width: 100vw;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        pointer-events: auto;
        transition: transform 0.5s ease, opacity 0.5s ease;
        will-change: transform, opacity;
    }

    .suggest-content-container {
        position: relative;
        z-index: 10;
        margin-top: 10vh;
        margin-bottom: 10vh;
        padding: 10vh 0;
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
    .parallax-container {
        position: relative;
        z-index: 5; /* Lower z-index so it appears between content and movie-calendar */
        padding: 3rem 0;
        overflow: visible; /* Allow content to be visible outside container */
        margin-top: -20vh; /* Adjusted to start appearing as you scroll down */
        margin-bottom: 15vh; /* Space before button */
        transition: transform 0.8s ease-in-out;
        will-change: transform;
        min-height: 50vh; /* Ensure enough height for scrolling effect */
    }
    .parallax-container2 {
        position: relative;
        z-index: 5; /* Lower z-index so it appears between content and movie-calendar */
        padding: 3rem 0;
        overflow: visible; /* Allow content to be visible outside container */
        margin-top: 15vh; /* Space after button */
        transition: transform 0.8s ease-in-out;
        will-change: transform;
        min-height: 50vh; /* Ensure enough height for scrolling effect */
    }
    .suggest-content-container {
        display: flex;
        justify-content: center;
        width: 100%;
        position: relative;
        z-index: 15;
        padding: 5vh 0;
        margin: 0; /* Reset margins to control spacing with padding */
    }
