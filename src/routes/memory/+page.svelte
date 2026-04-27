<script>
    let cards = []
    for (let i = 0; i < 12; i++) {
        cards.push(i % 7)
    }

    let imgs = [
        "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRAzUWGK5YqAzftu_vnf4obWNlhXKMK-D8L1w&s",
        "https://thumbs.dreamstime.com/z/shirtless-svart-man-28054453.jpg",
        "https://vkmedia.imgix.net/E9mTTCQjhHE8otVTwJtTPlw5jQc.jpg?auto=format,compress&w=1280&rect=0.06125,0,0.88,1",
        "https://az729104.cdn.laget.se/11232450.jpg;width=600;mode=crop;scale=both;anchor=middlecenter;v=1",
        "https://umeaok.se/wp-content/uploads/2024/07/Trippel-1024x768.jpeg",
        "https://i1.sndcdn.com/artworks-000044489589-04b135-t500x500.jpg",
        "https://vkmedia.imgix.net/7ae95469-b7c9-574f-920d-9e3f9ac00d7b.jpg?auto=format,compress&w=553&h=311&crop=faces,edges&fit=crop"
    ]

    let back = "https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Question_mark.svg/768px-Question_mark.svg.png"

    let bluePoints = 0
    let redPoints = 0


    let blueTurn = true
</script>


<aside class="blue">
    <p>{bluePoints}</p>
</aside>

<aside>
    <p>{redPoints}</p>
</aside>


<aside class="turn" class:blue={blueTurn}></aside>


<main>
    {#each cards as card}
        <div class="picture">
            <img src={imgs[card]} alt="front" />
            <img src={back} alt="back" />
        </div>
    {/each}
</main>


<style>


.picture img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    backface-visibility: hidden;
}

.back {
    transform: rotateY(90deg);
}

.front {
    transform: rotateY(180deg);
}

    main {
        display: grid;
        grid-template-columns: repeat(3, 100px);
        grid-template-rows: repeat(4, 100px);
        gap: 5px;
    }

    .picture {
        border: 1px solid black;
        position: relative;
        width: 100%;
        height: 100%;
        overflow: hidden;
    }

    .picture img {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    aside {
        width: 100px;
        height: 100px;
        position: fixed;
        bottom: 10px;
        right: 10px;
        background-color: red;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .blue {
        background-color: blue;
        left: 10px;
        right: auto;
    }

    /* ⭐ styling för turn-rutan */
    .turn {
        box-shadow: 0 0 10px 10px yellowgreen;
        z-index: -1;
    }

    p {
        font-size: 30px;
        color: white;
    }
</style>
