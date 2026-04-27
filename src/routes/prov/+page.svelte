<main>
    <div class = container0></div>
    <div class = container1></div>
    <div class = container2></div>
    <div class = container3></div>
    <div class = container4></div>
    <div class = container5></div>
   
</main>

<style>

    main{
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
    }
    .container0{
        border: solid 10px red;
            width:400px;
            height:400px;
            background-color:red;
    }
    .container1{
    border: solid 10px aqua;
        width:400px;
        height:400px;
        background-color: aqua;
        -ms-flex-align:center;
    }
    .container2{
    border: solid 10px green;
        width:400px;
        height:400px;
        background-color: green;
        -ms-flex-direction: column;
    }

    .container3{
    border: solid 10px orange;
        width:400px;
        height:400px;
        background-color: orange;
    }
   .container4{
    border: solid 10px purple;
        width:400px;
        height:400px;
        background-color: purple;
   }

      .container5{
    border: solid 10px yellow;
        width:400px;
        height:400px;
        background-color: yellow;
   }


</style>