<div class="hero">

    <!-- panels -->
    <div class="panel">
        <div class="item">
            <img src="/img1.jpg" alt="">
        </div>
        <div class="item">
            <img src="/img2.jpg" alt="">
        </div>
        <div class="item">
            <img src="/img3.jpg" alt="">
        </div>
        <div class="item">
            <img src="/img4.png" alt="">
        </div>
    </div>

    <!-- thumbs -->
    <div class="thumbs">
        <div class="item">
            <img src="/img1.jpg" alt="">
        </div>
        <div class="item">
            <img src="/img2.jpg" alt="">
        </div>
        <div class="item">
            <img src="/img3.jpg" alt="">
        </div>
        <div class="item">
            <img src="/img4.png" alt="">
        </div>
    </div>
</div>

<script>
    import { onMount } from 'svelte';

    onMount(() => {

        // Call the nextSlider function every 5 seconds
        const interval = setInterval(nextSlider, 5000);
        return () => clearInterval(interval);
    });

    // Function to move the first item to the end of the list and the first thumbnail to the end of the thumbs
    function nextSlider(){

        // Move the first item to the end of the list
        const list = document.querySelector('.hero .panel');
        const items = document.querySelectorAll('.hero .panel .item');

        const firstItem = items[0];
        list?.appendChild(firstItem);

        // Move the first thumbnail to the end of the thumbs
        const thumbs = document.querySelector('.hero .thumbs');
        const thumbItems = document.querySelectorAll('.hero .thumbs .item');

        const firstThumbItem = thumbItems[0];
        thumbs?.appendChild(firstThumbItem);
    }
</script>

<style>
.hero{
    width: 100%;
    height: 800px;
    position: relative;
    background-image: url("https://cdn.wallpapersafari.com/53/78/P1BRkw.jpg");
    background-size: cover;
    background-repeat: no-repeat;
}

/* panel */
.hero .panel .item{
    width: 100%;
    height: 100%;
    position: absolute;
    bottom: 0px;
    left: 0%;
    border-radius: 0;
}
.hero .panel .item img{
    height: 100%;
    width: 100%;
    max-width: 500px;
    object-fit: cover;
    border-radius: 0;
    
}

/* panel animation */
.hero .panel .item:nth-child(1){
    z-index: 3;
    left: 70%;
    bottom: 50px;
    width: 150px;
    height: 220px;
    animation: show 1s forwards;
}
/* .hero .panel .item:nth-child(1) img{
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 10px;
    
} */
@keyframes show {
    to{
        width: 100%;
        height: 100%;
        left: 0;
        bottom: 0;
        border-radius: 0;
        z-index: 2;
    }
}

/* thumbs */
.hero .thumbs{
    display: flex;
    position: absolute;
    bottom: 50px;
    left: 70%;
    gap: 10px;
    z-index: 5;
}
.hero .thumbs .item{
    width: 150px;
    height: 220px;
    border-radius: 10px;
    position: relative;
}
.hero .thumbs .item img{
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 10px;
}

/* Thumbs animation */
.hero .thumbs .item:nth-child(1) {
    overflow: hidden;
    opacity: 0;
    animation: hideThumb 1s linear 1 forwards;
}
@keyframes hideThumb{
    to{
        width: 0
    }
}
</style>