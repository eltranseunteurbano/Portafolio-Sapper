<script>

    import { flip } from 'svelte/animate'
    import { onDestroy } from 'svelte'

    import Redes from '../assets/scritps/Redes'

    import Logo from '../components/Logo'
    import Icono from '../components/Icono'
    import Header from '../components/Header'

    $:description = 'React Frontend Developer';

    const professions = [ 'React Frontend Developer', 'Diseñador de Interfaces', 'Svelte Frontend Developer', 'Jugador de Ultimate', 'Realizador Audiovisual']
    let position = 0;

    const interval = setInterval( function () {
        description = professions[position]
        position += 1;
        if(position >= 4) { position = 0 }
    }, 1500);

    onDestroy( () => clearInterval(interval))


    
</script>

<style>
    .Banner {
        width: 100vw;
        height: 90vh;

        background-image: url('./images/degradedBackground.svg');
        background-repeat: no-repeat;
        background-size: cover;
        background-position: bottom;

        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;

        padding: 20px;
        box-sizing: border-box;
        
        margin-bottom: 150px;
    }

    .Banner__logo {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .Banner__logo__image {
        width: 60%;
        margin-bottom: 50px;
    }

    .Banner__logo__text {
        color: var(--color-white);
        text-align: center;
    }

    .Banner__logo__text h1 {
        font-weight: 600;
        font-family: var(--font-open);
        text-transform: uppercase;
        margin-bottom: 20px;
        font-size: 25px;
    }

    .Banner__logo__text span{
        font-family: var(--font-nunito);
        margin-bottom: 0;
    }

    .Redes {
        display: flex;
        justify-content: flex-start;
        align-items: flex-start;
    }

    img {
        width: 100%;
    }

    .Mouse {
        margin-bottom: 80px;
    }

    .Mouse__down {
        animation: down 1.5s ease-in-out infinite;
    }

    @keyframes down {
        0% {
            opacity: 0;
            transform: translateY(0)

        }

        50% {
            opacity: 1;
        }

        100% {
            opacity: 0;
            transform: translateY(10px)
        }
    }

    @media only screen and (min-width: 768px) {
.Banner {
    height: 95vh;
}
    }

</style>

<section class="Banner">
    <Header />
    
    <div class="Banner__logo">
        <div class="Banner__logo__image"> <img src="/images/logo.svg" alt="Logo Jaime Burbano"></div>
        <div class="Banner__logo__text">
            <h1> Jaime Burbano</h1>
            <span >{description}</span>
        </div>
    </div>

    <div class="Redes">
    
        {#each Redes as item}
            <Icono name = { item.name } url = { item.url } image = { item.image } />
        {/each}

    </div>

    <div class="Mouse">
        <svg width="20" height="34" viewBox="0 0 20 34" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect x="2" y="2" width="16" height="30" rx="8" stroke="#F5F5F5" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
            <rect class="Mouse__down" x="8" y="8" width="4" height="5" rx="2" fill="#F5F5F5"/>
        </svg>
    </div>

</section>