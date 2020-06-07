<script>
    import { Redes } from '../assets/scripts/DataObjects'
    import Icono from '../components/Icono'

</script>

<style>
    footer {
        width: 100%;
        min-height: 150px;
        background-color: var(--color-black);

        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        padding: 40px 0;
        box-sizing: border-box;
    }

    h1 {
        color: var(--color-white);
        font-family: var(--font-nunito);
        font-size: 20px;
        letter-spacing: 1px;
        font-weight: bolder;
        margin-bottom: 15px;
    }

    p { 
        color: var(--color-white);
        font-family: var(--font-nunito);
        font-size: 16px;
        font-weight: regular;
        opacity: .7;
    }

    .Redes {
        display: flex;
        justify-content: flex-start;
        align-items: flex-start;
        margin-bottom: 20px;
    }

</style>

<footer >
    <div class="Redes">
        {#each Redes as item}
            <Icono name = { item.name } url = { item.url } image = { item.image } type="footer"/>
        {/each}
    </div>
    <h1> JAIME BURBANO</h1>
    <p>Todos los derechos reservados</p>
</footer>