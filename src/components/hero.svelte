<div class="hero">
    <div class="panels">
        <div class="panel" style="background-image: url('/img1.jpg');padding-bottom: 100px">
            <div class="row px-0" style="height: 100%;padding-top: 100px; z-index: 3; position: relative">
                <div class="col-lg-4 col-md-6 col-sm-12 d-flex justify-content-center p-0">
                    <img src="/img1.jpg" alt="" class="cover">
                </div>

                <div class="col-lg-8 col-md-6 col-sm-12 px-4 d-flex flex-column justify-content-end">
                    <h2 class="text-center text-md-start">Ranking: top 1</h2>
                    <h1 class="text-center text-md-start mg-name">Manga Name</h1>
                    <h5 class="text-center text-md-start mg-author">Authorize</h5>
                    <h5 class="text-center text-md-start mg-genres">Genres</h5>
                    <p class="desc">Lorem ipsum dolor sit amet consectetur adipisicing elit. Adipisci sequi molestias mollitia exercitationem officia quam hic quia praesentium, consectetur tempore commodi officiis maxime in corporis delectus debitis blanditiis. Tempora dicta consectetur incidunt, voluptatem quo eligendi libero eos ratione placeat nulla exercitationem est iusto nisi molestiae fugit pariatur. Iure nihil, enim reprehenderit voluptatum, voluptate explicabo quia doloribus vitae, vero numquam ipsam.</p>
                    <div class="d-grid" style="padding: 0 50px;">
                        <button class="btn btn-success">Read now</button>
                    </div>
                </div>
            </div>
            
        </div>
    </div>
</div>

<style>
    .hero{
        width: 100%;
        height: 100%;
    }
    .hero .panels{
        width: 100%;
        height: 100%;
    }
    .hero .panel{
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
    }
    .hero .panel::before{
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: #0004;
        backdrop-filter: blur(8px);
        /* z-index: 0; */
    }
    .cover{
        width: 80%;
        border-radius: 10px;
        box-shadow: 0 0 10px 5px #0008;
    }
    p.desc{
        text-align: justify;
        display: -webkit-box;
        -webkit-line-clamp: 4;
        line-clamp: 4;
        -webkit-box-orient: vertical;
        overflow: hidden;
    }
    .mg-name, .mg-author{
        display: -webkit-box;
        -webkit-line-clamp: 1;
        line-clamp: 1;
        -webkit-box-orient: vertical;
        overflow: hidden;
    }
    .mg-genres{
        display: -webkit-box;
        -webkit-line-clamp: 2;
        line-clamp: 2;
        -webkit-box-orient: vertical;
        overflow: hidden;
    }
</style>