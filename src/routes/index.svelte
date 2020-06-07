<script>
    import Banner from '../containers/Banner'
    import Welcome from '../containers/Welcome'
    import WhatIDo from '../containers/WhatIDo'
    import LastProjects from '../containers/LastProjects'
    import Footer from '../containers/Footer'
</script>
<svelte:head>
    <title>El Transeunte Urbano | Jaime Burbano</title>
</svelte:head>

<style>

    :global(.title) {
         color: var(--main-color);
        font-family: var(--font-open);
        font-weight: bolder;
        font-size: 25px;
        letter-spacing: .4px;
        margin-bottom: 30px;
        text-align: center;
        text-transform: uppercase;
    }

    :global(a::selection) {
        background: var(--second-color);
        color: var(--color-white);
    }

    :global(h1::selection) {
        background: var(--main-color);
        color: var(--color-white);
    }

    :global(p::selection), :global(h2::selection) {
        background: var(--color-black);
        color: var(--color-white);
    }

    :global(img) {
        pointer-events: none;
        user-select: none;
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

    

    .index {
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
    }

    

</style>

<main class="index">
    <Banner />
    <Welcome />
    <WhatIDo />
    <LastProjects />
</main>
<Footer />