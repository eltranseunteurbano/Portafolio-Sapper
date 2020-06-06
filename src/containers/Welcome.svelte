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

    h1 {
         color: var(--main-color);
        font-family: var(--font-open);
        font-weight: bolder;
        font-size: 25px;
        letter-spacing: .4px;
        margin-bottom: 30px;
        text-align: center;
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

    a {
        color: var(--second-color);
        font-family: var(--font-open);
        background: var(--color-white);
        border: solid 2.5px var(--second-color);
        font-weight: bolder;
        cursor: pointer;
        text-decoration: none;
        text-align: center;
        text-transform: uppercase;
        border-radius: 4px;
        padding: 15px 20px;
        box-sizing: border-box;
        width: 100%;
        max-width: 400px;
        transition: all .4s;
    }

    a:hover {
        background: var(--second-color);
        color: var(--color-white);
    }
</style>

<section class="Welcome">
    <h1 class="title">¡HOLA! SOY JAIME BURBANO</h1>
    <p>{Description}</p>
    <a href="/PDF/CV - Jaime Burbano.pdf" download="Jaime Burbano - CV" target="_blank"> Descargar Hoja de Vida</a>
</section>