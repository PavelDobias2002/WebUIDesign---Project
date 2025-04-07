@media (max-width: 992px) {
    .movie-container {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 20px;
        width: 90%;
        margin: 2rem auto;
        padding: 1.5rem;
        background-color: rgba(104, 165, 106, 0.6);
        border-radius: 30px;
    }
    
    .title {
        grid-area: 1 / 1 / 2 / 3;
        text-align: center;
    }
    
    .image {
        grid-area: 2 / 1 / 3 / 3;
        width: 100%;
        height: auto;
    }
    
    .genre {
        grid-area: 3 / 1 / 4 / 2;
    }
    
    .director {
        grid-area: 3 / 2 / 4 / 3;
    }
    
    .production {
        grid-area: 4 / 1 / 5 / 2;
    }
    
    .cast {
        grid-area: 4 / 2 / 5 / 3;
    }
    
    .description {
        grid-area: 5 / 1 / 6 / 3;
    }
    
    .trailer {
        grid-area: 6 / 1 / 7 / 3;
    }
    
    .movie-container .title h3 {
        font-size: 2.5rem;
    }
    
    .movie-container > div {
        height: auto;
        min-height: fit-content;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
    }
    
    .movie-container > div h3 {
        margin-bottom: 1rem;
    }
    
    .movie-container > div p {
        margin: 0.5rem 0;
    }
}

.trailer {
    position: relative;
    width: 100%;
    padding-top: 56.25%; /* 16:9 Aspect Ratio */
    overflow: hidden;
}

.trailer iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: none;
    border-radius: 30px;
}

.trailer h3 {
    position: relative;
    z-index: 1;
    margin-bottom: 1rem;
}
