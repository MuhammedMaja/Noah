<script>

   
function handleSubmit(){
    alert("Välkommen "+ name)
}
</script>


<main>

<div class = container>
<h1>logga in</h1>

<form on:submit|preventDefault={handleSubmit}>




<label for="e-mail">E-mail:</label>
<input type="text" id="e-mail">
<label for="name">lösenord:</label>
<input type="password" id="name" >

<input type="submit" value="reg">

</form>   


	<a href="register"> har du inte ett konto? </a>

  


</div>


        
</main>

<style>

    form{

        padding: 2em;
        background-color: rgba(255,255,255,0.1);
    }

.container{
        /* Skapar en ram med rundade kanter */
        border: solid 5px rosybrown;
        border-radius: 10px;
        /* Responsiv storlek som anpassar sig till skärmen */
        width: 35%;
        height: 80%;
        background-color: #3a2e3b;
        /* Centrerar behållaren på sidan */
        margin: auto;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-evenly;
}     
 main{
        /* Sätter en bakgrundsbild på behållaren */
        background-image: url("https://t4.ftcdn.net/jpg/05/21/65/59/360_F_521655929_N80d5GaCQJ2VP073PfTXJTe9mkvsNtHE.jpg");
        /* Gör att bilden täcker hela behållaren */
        background-size: cover;
        /* Sätter bredden och höjden till 100% av sidan */
        width: 100%;
        height: 100%;
        /* Ger 5% padding så innehållet inte ligger mot kanten */
        padding: 5%;
        
        
    

        
    }
</style>
