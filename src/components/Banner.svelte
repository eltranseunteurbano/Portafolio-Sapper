<script>

    import { fly } from 'svelte/transition'

    import Logo from './Logo'
    import Icono from './Icono'
    import Header from './Header'

    let redes = [
        {
            name: 'Linkedin',
            url: 'https://www.linkedin.com/in/eltranseunteurbano/',
            image: '/images/iconos/linkedin.svg'
        },{
            name: 'Behance',
            url: 'https://www.linkedin.com/in/eltranseunteurbano/',
            image: '/images/iconos/behance.svg'
        },{
            name: 'Git Hub',
            url: 'https://www.linkedin.com/in/eltranseunteurbano/',
            image: '/images/iconos/github.svg'
        },{
            name: 'Filmmaking',
            url: 'https://www.linkedin.com/in/eltranseunteurbano/',
            image: '/images/iconos/filmmaking.svg'
        },{
            name: 'Dribbble',
            url: 'https://www.linkedin.com/in/eltranseunteurbano/',
            image: '/images/iconos/dribbble.svg'
        },{
            name: 'Instagram',
            url: 'https://www.linkedin.com/in/eltranseunteurbano/',
            image: '/images/iconos/instagram.svg'
        },{
            name: 'Whats App',
            url: 'https://www.linkedin.com/in/eltranseunteurbano/',
            image: '/images/iconos/whatsapp.svg'
        },
    ]
</script>

<style>
    .Banner {
        width: 100vw;
        height: 100vh;

        background-image: url('./images/degradedBackground.svg');
        background-repeat: no-repeat;
        background-size: cover;
        background-position: bottom;

        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;

        padding: 20px;
        padding-bottom: 20%;
        box-sizing: border-box;
    }

    .Banner__logo {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .Banner__logo__image {
        width: 50%;
    }

    .Banner__logo__text {
        color: var(--color-white);
        text-align: center;
    }

    .Banner__logo__text h1 {
        font-weight: 600;
        font-family: var(--font-open);
        text-transform: uppercase;
        margin-bottom: 0;
        letter-spacing: 1.2px;
    }

    .Banner__logo__text h1 {
        font-family: var(--font-nunito);
        margin-bottom: 0;
    }

    .Redes {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    img {
        width: 100%;
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

</style>

<section class="Banner">
    <Header />
    
    <div class="Banner__logo">
        <div class="Banner__logo__image"> <img src="/images/logo.svg" alt="Logo Jaime Burbano"></div>
        <div class="Banner__logo__text">
            <h1> Jaime Burbano</h1>
            <span>Front end Developer</span>
        </div>
    </div>

    <div class="Redes">
    
        {#each redes as item}
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