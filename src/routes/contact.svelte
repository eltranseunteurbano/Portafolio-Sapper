<script>
    import Footer from '../containers/Footer'
    import Header from '../components/Header'
    import Icono from '../components/Icono'
    import { DescriptionContact } from '../assets/scripts/Text'
    import { Redes } from '../assets/scripts/DataObjects'
</script>

<style>
    :global(h1::selection) {
        background: var(--main-color);
        color: var(--color-white);
    }
    :global(.button) {
        width: 100%;
        max-width: 400px;
        
        color: var(--second-color);
        font-weight: bolder;
        font-family: var(--font-open);
        
        text-decoration: none;
        text-align: center;
        text-transform: uppercase;
        
        border-radius: 4px;
        background: var(--color-white);
        border: solid 2.5px var(--second-color);
        
        padding: 15px 20px;
        box-sizing: border-box;
        
        cursor: pointer;
        transition: all .4s;
    }
    :global(.button:hover) {
        background: var(--second-color);
        color: var(--color-white);
    }
    :global(p::selection), :global(h2::selection) {
        background: var(--color-black);
        color: var(--color-white);
    }
    .Contact {
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
        padding: 20px;
        padding-top: 40px;
        box-sizing: border-box;
        width: 100vw;
        min-height: calc( 100vh - 80px );
    }
    .wrapper {
        width: 100%;
        min-height: 80%;
        max-width: 1500px;
        display: grid;
        grid-template: repeat(6, auto) / 1fr;
        grid-template-areas: "titulo" "imagen" "text" "redes" "data" "footer";
        grid-gap: 20px; 
    }
    .title h1 {
        color: var(--main-color);
        font-family: var(--font-open);
        font-weight: bolder;
        font-size: 25px;
        margin-bottom: 50px;
        letter-spacing: .4px;
        text-align: center;
        text-transform: uppercase;
    }
    .title {
        grid-area: titulo;
    }
    .wrapper__img, .wrapper__text, .contact-data, .Redes{
        margin: auto;
    }
    .wrapper__img {
        margin-bottom: 20px;
        width: 200px;
        grid-area: imagen;
    }
    img {
        border-radius: 200px;
        width: 100%;
        pointer-events: none;
        user-select: none;
    }
    .Redes {
        display: flex;
        justify-content: flex-start;
        align-items: flex-start;
        padding: 20px 0;
        box-sizing: border-box;
        grid-area: redes;
    }
    .wrapper__text {
        color: var(--color-black);
        font-family: var(--font-nunito);
        max-width: 650px;
        text-align: center;
        font-size: 18px;
        line-height: 25px;
        grid-area: text;
    }
    footer {
        grid-area: footer;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    footer h1 {
        color: var(--color-black);
        font-family: var(--font-nunito);
        font-size: 20px;
        letter-spacing: 1px;
        font-weight: bolder;
        margin-bottom: 15px;
        text-align: center;
    }
    footer p { 
        color: var(--color-black);
        font-family: var(--font-nunito);
        font-size: 16px;
        font-weight: regular;
        opacity: .7;
        text-align: center;
    }
    .contact-data a{
        display: block;
        text-decoration: none;
        text-align: center;
        margin-bottom: 10px;
        font-weight: regular;
        font-family: var(--font-nunito);
        color: var(--main-black);
        font-size: 18px;
        grid-area: data;
    }
    .contact-data a:first-child {
        font-weight: bolder;
        font-family: var(--font-nunito);
        color: var(--main-color);
        font-size: 20px;
    }
    .contact-data a:last-child {
        font-size: 14px;
    }
    @media only screen and (min-width: 768px) {
        .Contact {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }
        .wrapper {
            grid-template: 100px 150px 150px 80px 120px / 400px 500px;
            grid-template-areas: "titulo imagen" "text imagen" "redes imagen" "data imagen" "footer footer";
            grid-column-gap: 70px;
        }
        .wrapper__img {
            margin: auto;
            width: 350px;
        }
        img {
            border-radius: 4px;
        }
    }
</style>

<svelte:head>
    <title>Contacto - El Transeunte Urbano | Jaime Burbano</title>
</svelte:head>


<Header origin={"contact"} />
<main class="Contact">

    <div class="center">

        <article class="wrapper">
            <div class="title"><h1>CONTACTO</h1></div>

            <div class="wrapper__img">
                <img src="/images/profile.png" alt="Foto de Jaime Burbano" />
            </div>

            <p class="wrapper__text">{DescriptionContact}</p>

            <div class="Redes">
            {#each Redes as item}
                <Icono name = { item.name } url = { item.url } image = { item.image } type="footer"/>
            {/each}
            </div>

            <div class="contact-data">
                <a href="mailto:hablemos@jaimeburbano.com?subject=Hola Estoy Interesado/a en..." rel="noopener" target="_blank">hablemos@jaimeburbano.com</a>
                <a href="https://api.whatsapp.com/send?573162580525" rel="nooper" target="_blank">+57 316 258 0525</a>
                <a href="https://www.google.com/maps/place/Cali,+Valle+del+Cauca" rel="nooper" target="_blank">CALI - COLOMBIA</a>
            </div>
            
            <footer>
                <h1> JAIME BURBANO</h1>
                <p>Todos los derechos reservados</p>
            </footer>

        </article>

    </div>
</main>