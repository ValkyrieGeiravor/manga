<div class="image-wrapper">
    <img src="/img1.jpg" alt="Ảnh gốc">
    <div class="image-extension"></div>
</div>

<style>
    .image-wrapper {
        position: relative;
        display: inline-block;
    }

    .image-wrapper img {
        display: block;
        max-width: 100%;
        height: auto;
    }

    .image-extension {
        position: absolute;
        top: 0;
        right: 0;
        width: 80px; /* độ dài kéo ra */
        height: 100%;
        background: linear-gradient(to right, rgba(255,255,255,0), rgba(255,255,255,1));
        filter: blur(12px);
        transform: scaleX(1.5); /* làm hiệu ứng kéo giãn ngang */
        transform-origin: left;
        pointer-events: none;
    }

</style>