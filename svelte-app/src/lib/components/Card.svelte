<script>
    // Props allow customization of card title and description
    export let title = "Card Title";
    export let description = "This is a brief description of the card. ";
    export let image = "/default-placeholder.jpg";
 </script>
    
<!-- Card1 container-->
<div class="card">
<!-- Placeholder image -->
 <img src={image} alt={title} class="card-image">
<!-- Card content-->
<div class="content">
    <h2>{title}</h2>
    <p>{description}</p>
    </div>
</div>



<style>
    /* Card container with smooth hover effects */
    .card {
    position: relative;
    max-width : 250px;
    height : 215px;  
    background-color : #000000;
    margin : 30px 10px;
    padding : 20px 15px;
  
    display : flex;
    flex-direction : column;
    box-shadow : 0 5px 20px rgba(0,0,0,0.5);
    transition : 0.3s ease-in-out;
    border-radius : 15px;
    }

    .card > img {
        position : relative;
    width : 260px;
    height : 260px;
  
    top : -50%;
    left: 8px;
    box-shadow : 0 5px 20px rgba(0,0,0,0.2);
    z-index : 1;
     max-width : 100%;
    border-radius : 15px;
    }

    /* Content Styling: Padding for better spacing */
    .content {
        position : relative;
  top : -140px;
  padding : 10px 15px;
  color : #ffffff;
  text-align : center;
  
  visibility : hidden;
  opacity : 0;
  transition : 0.3s ease-in-out;
    }

    /* Title Styling */
    .content h2 {
        font-size: 1.2rem;
       
    }

    /* Description Styling */
    .content p {
        font-size: 1rem;
    }
    .card:hover {
        height : 350px;  
    }
    .card:hover .content{
        margin-top : 30px;
        visibility : visible;
        opacity : 1;
        transition-delay: 0.2s;
       
    }
    .card:nth-child(even):hover .content{
        border: solid 1px rgb(202, 26, 176);
         border-radius:20px;
    }
    .card:nth-child(odd):hover .content{
        border: solid 1px rgb(26, 202, 111);
         border-radius:20px;
    }


</style>
