
<script>
   let varor = $state([{ name:"Mjölk" , valter: true }, {name:"ägg", valter: true}, {name:"kyckling" , valter:true}, {name: "papper" , valter:true }, {name: "penna" , valter:true}])



</script>






<main>

</main>

    <div class='container'> 
        <h1>Shopping list</h1>
    

    




<form>
    <input type="text" id="name">
</form>

<div class="categories_container">


    <section>
    <h2>Varor att köpa</h2>
        <ol>
            {#each varor as vara}
            {#if vara.valter==false}
                <li>
                    
                    
                    {vara.name}
                    <button onclick={vara.valter=true}>
                        <p>x</p>
                    </button>

                </li> 
            {/if}
            {/each}
           
           
        </ol>
    </section>
    <section>
    <h2>Köpta varor</h2>
        <ul>
            {#each varor as vara}
            {#if vara.valter==true}
                <li>
                    { vara.name}
                    <button onclick={vara.valter=false}> 
                        <p>x</p>


                    </button>
                </li>
            {/if}
            {/each }
        </ul>

    </section>



</div>
    </div>


<sections>
</sections>


<style>
    .container h2{
        justify-self: center;
        background-color: rgb(231, 62, 93);
    }

    .container h1{
        justify-self: center;
        background-color: rgb(231, 62, 93);
    }

    .categories_container{
        background-color: rgb(241, 119, 141);
        width: 100%;
        grid-template-columns: repeat(2,1fr);
        display: grid;
    }

    
 .categories_container section:nth-child(even){  /* vilket barn vill vi styla? */
    background-color: rgba(0, 0, 0, 0.1) /* svart bakgrund med 10% opacitet */
  }
 
  .categories_container section:nth-child(odd){  /* vilket barn vill vi styla? */
    background-color: rgba(0, 0, 0, 0.3) /* svart bakgrund med 30% opacitet */
  }

      
.container{
display: grid;
grid-template-rows: 1fr 8fr 1fr;
grid-template-columns: 1fr;
    margin: auto;
    justify-content: center;

    background-color: rgb(254, 106, 106);
    width: 60vw;
    height: 70vh;
    border-radius: 20px;
}
     </style>   