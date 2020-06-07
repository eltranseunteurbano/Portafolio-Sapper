<script>
    import ViewProject from '../components/ViewProject'
</script>

<style>

    .LastProject{
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;

        width: 100%;
        max-width: 1500px;
        margin-bottom: 150px;
    }

    .wrapper {
        display: grid;
        grid-template: repeat(4, 300px) / 1fr;
        grid-gap: 40px;
        margin-bottom: 60px;
    }

    .wrapper:hover .wrapper__item:not(:hover) {
        filter: grayscale(100%);
    }

    @media only screen and ( min-width: 700px) and (max-width: 1390px) {
        .wrapper {
            grid-template: 1fr / repeat(2, 300px);
        }
    }

    @media only screen and ( min-width: 1390px){
        .wrapper {
            grid-template: 1fr / repeat(4, 300px);
        }
    }


</style>

<section class="LastProject">

    <h1 class="title">Últimos Proyectos</h1>

    <article class="wrapper">
    <div class="wrapper__item"> <ViewProject /> </div>
    <div class="wrapper__item"> <ViewProject /> </div>
    <div class="wrapper__item"> <ViewProject /> </div>
    <div class="wrapper__item"> <ViewProject /> </div>
    </article>

    <a class="button" href="/projects" rel="prefetch">VER TODOS LOS PROYECTOS</a>

</section>