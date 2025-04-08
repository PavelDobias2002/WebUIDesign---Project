<script>
    // Props allow customization of card title and description
    export let title = "Card Title";
    export let description = "This is a brief description of the card. ";
    export let image = "{base}/default-placeholder.jpg";

    // import base to prefix local paths
    import { base } from '$app/paths';
 </script>

 <!-- Card2 container-->
<div class="card2">
    <!-- Placeholder image -->
    <img src={image} alt={title} class="card-image">
    <!-- Card content-->
    <div class="content2">
        <h2>{title}</h2>
        <p>{description}</p>
        </div>
    </div>

    <style>
           /*card2 styling*/
    /* Card container with smooth hover effects */
    .card2 {
        /*background: white;*/
        border-radius: 10px; /* Rounded corners */
        /*border: 2px solid #000000;*/
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1); /* Subtle shadow */
        overflow: hidden;
        width: 250px;
        text-align: center;
        transition: transform 0.3s ease, box-shadow 0.3s ease; /* Smooth transitions */
    }

    /* Advanced Selector: Direct Child Combinator (>)
       This ensures that only direct `img` elements inside `.card` get these styles */
    .card2 > img {
        width: 100%; /* Responsive width */
        height: auto; /* Maintain aspect ratio */
        border-radius: 8px 8px 0 0; /* Round only the top corners */
        padding:2rem;
    }

    /* Content Styling: Padding for better spacing */
    .content2 {
        padding: 1.5rem;
    }

    /* Title Styling */
    .content2 h2 {
        color: black;
        font-size: 1.2rem;
        margin-bottom: 0.5rem;
    }

    /* Description Styling */
    .content2 p {
        font-size: 1rem;
        color: #000000;
        font-family:"Exo 2", sans-serif;
    }

    /* Pseudo-Class: Hover Effect
       Adds a subtle lift when hovering over the card */
    .card2:hover {
        transform: translateY(-10px);
        transform:rotate(5deg);
        box-shadow: 0 6px 15px rgba(0, 0, 0, 0.15);
    }

    /* Pseudo-Element: Adds a thin underline before the card title
       Creates a subtle decorative effect to enhance UI */
    .content2 h2::before {
        content: "";
        display: block;
        width: 40%;
        height: 2px;
        background: #000000;
        margin: 0 auto 10px auto;
        transition: width 0.3s ease-in-out;
    }

    /* When .card is hovered, expand the decorative effect to 80% */
    .card2:hover .content2 h2::before {
        width: 80%; /* Expanded width on hover */
    }
    </style>
    