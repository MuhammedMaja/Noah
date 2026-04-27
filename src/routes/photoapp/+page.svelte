<h1>
    photoapp
</h1>


<script>
    
    let image = "https://picsum.photos/id/70/367/267"
    let photo = "https://picsum.photos/id/88/367/267"
    let picture = "https://picsum.photos/id/93/367/267"
</script>





<div class="photos">
    <div class='image-wrapper'>
        <img src={image} alt="hej">
    </div> 
    <div class='image-wrapper'>
       <img src={photo} alt="där">
    </div> 
    <div class='image-wrapper'>
        <img src={picture} alt="Lisa">
    </div> 
</div>
<style>
    
h1{
    text-align: center;
    font-size: 50px;
    margin: 20px;
    color: rgb(23, 20, 20);
}
    .photos{
        flex-wrap: wrap;
        display:flex;
        max-width: 90vw;
          align-items:center;
        justify-content:center;
    }
    .image-wrapper img{ 
        width: 100%;
        height: 100%;
        border-radius: 20px;
        background-color: rgb(0, 0, 0);
        box-shadow: 4px 8px 2px rgba(0,0,0,0.2);
    }

    .image-wrapper{
                flex:1;
height: 400px;
margin: 10px;
    }
    .image-wrapper:hover{ 
        flex:2;
    }
    .image-wrapper:active{ 
        transform: scale(0.9);
        
    }

    
    
</style>