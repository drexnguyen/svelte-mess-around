<script>
    import Button from "../../lib/components/Button.svelte";

    import img1 from "#lib/assets/Chungus1.png";
    import img2 from "#lib/assets/Chungus2.png";
    import img3 from "#lib/assets/Chungus3.png";
    import img4 from "#lib/assets/FruitJuiceChunguy.png";
    import img5 from "#lib/assets/Chungus4.png";


    const imgCollection = [
        {id: 1, src:img1, alt: "Chungus1"},
        {id: 2, src:img2, alt: "Chungus2"},
        {id: 3, src:img3, alt: "Chungus3"},
        {id: 4, src:img4, alt: "The Sillies!"},
        {id: 5, src:img5, alt: "Dead Chungus"}
    ]

    let currentImg = $state(getRandomImg());

    function getRandomImg() {
        const randomIndex = Math.floor(Math.random() * imgCollection.length);
        return imgCollection[randomIndex];
    }

    function getNextImg() {
        currentImg = getRandomImg();
    }

    $inspect(currentImg);
</script>

<div id="randomizer-container"> 
    <div>
        <img src={currentImg.src} alt={currentImg.alt}>
    </div>
    <div>
        <Button variant="primary" onclick={getNextImg}>Click Me!</Button>
    </div>
</div>    

<style>
    #randomizer-container {
        display: flex;
        place-items: center;
        flex-direction: column;
        padding: 3em;
    }

    div {
        padding: 2rem;
    }
    img {
        height: 50vh;
    }
</style>