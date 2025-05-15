<!-- carousel --> 
<div class="carousel">

    <!-- Big panels -->
    <div class="list">
        <div class="item">
            <div class="ranking">1</div>

            <img src="/img1.jpg" alt="">
        </div>
        <div class="item">
            <div class="ranking">2</div>
            <img src="/img2.jpg" alt="">    
        </div>
        <div class="item">
            <div class="ranking">3</div>
            <img src="/img3.jpg" alt="">
        </div>
        
    </div>

    <!-- Small preview -->
    <div class="thumbs">
        <div class="item">
            <img src="/img1.jpg" alt="">

            <div class="ranking">1</div>
        </div>
        <div class="item">
            <img src="/img2.jpg" alt="">

            <div class="ranking">2</div>
        </div>
        <div class="item">
            <div class="ranking">3</div>

            <img src="/img3.jpg" alt="">

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
        const list = document.querySelector('.carousel .list');
        const items = document.querySelectorAll('.carousel .list .item');

        const firstItem = items[0];
        list?.appendChild(firstItem);

        // Move the first thumbnail to the end of the thumbs
        const thumbs = document.querySelector('.carousel .thumbs');
        const thumbItems = document.querySelectorAll('.carousel .thumbs .item');

        const firstThumbItem = thumbItems[0];
        thumbs?.appendChild(firstThumbItem);
    }
</script>

<style>
.carousel {
    position: relative;
    width: 100vw;
    height: 100vh;
    overflow: hidden;
    top: -60px;
}

/* List */
.carousel .list .item {
    width: 100%;
    height: 100%;
    position: absolute;
    bottom: 0px;
    left: 0%;
    border-radius: 0;
}
.carousel .list .item img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 0;
}
/* list animation */
.carousel .list .item:nth-child(1) {
    z-index: 3;
    width: 150px;
    height: 220px;
    left: 70vw;
    bottom: 20px;
    border-radius: 10px;
    animation: show 1s forwards;
}
@keyframes show {
    to{
        width: 100%;
        height: 100%;
        left: 0;
        bottom: 0;
        border-radius: 0;
    }
}

/* Thumbs */
.carousel .thumbs {
    /* width: 100vw;
    height: 100vh; */
    display: flex;
    position: absolute;
    bottom: 20px;
    left: 70vw;    
    gap: 10px;
    z-index: 10;
    border-radius: 10px;
}
.carousel .thumbs .item {
    width: 150px;
    height: 220px;
    border-radius: 10px;
    position: relative;
}
.carousel .thumbs .item img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 10px;
}
/* Thumbs animation */
.carousel .thumbs .item:nth-child(1) {
    overflow: hidden;
    opacity: 0;
    animation: hideThumb 1s linear 1 forwards;
}
@keyframes hideThumb{
    to{
        width: 0
    }
}
/* List ranking */

/* Thumb Ranking */
.carousel .thumbs .ranking {
    top: 0;left: 0;
    color: white;
    font-size: 20px;
    font-weight: bold;
    text-align: center;
    padding-top: 5px;
    z-index: 20;
    position: absolute;
    height: 50px;
    width: 50px;
    background: url('/ranking.png') no-repeat center;
    background-size: cover;
}
</style>