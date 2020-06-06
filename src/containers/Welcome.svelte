<script>

    import { Description } from '../assets/scritps/Text'

</script>

<style>

    .Welcome {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        margin-bottom: 150px;

        padding: 20px;
        box-sizing: border-box;
    }

    p {
        color: var(--color-black);
        font-family: var(--font-nunito);
        max-width: 650px;
        margin-bottom: 60px;
        text-align: center;
        font-size: 18px;
        line-height: 25px;
    }

</style>

<section class="Welcome">
    <h1 class="title">¡HOLA! SOY JAIME BURBANO</h1>
    <p>{Description}</p>
    <a class="button" href="/PDF/CV - Jaime Burbano.pdf" download="Jaime Burbano - CV" target="_blank"> Descargar Hoja de Vida</a>
</section>