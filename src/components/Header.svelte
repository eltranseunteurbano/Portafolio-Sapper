<script>
    import {fly, slide, blur, fade } from 'svelte/transition';
    import { goto } from '@sapper/app'

    import Logo from './Logo'
    import Bars from './Bars'
    import CloseHeader from './CloseHeader'
    import { Redes } from '../assets/scripts/DataObjects'
    import Icono from './Icono'

    $: showMenu = false;
    export let origin = 'index'

    function toggleMenu ( event ) {
        showMenu = event;
    }

    function onElementHeightChange(elm, callback){
        var lastWidth = elm.clientWidth, newWidth;
        (function run(){
            newWidth = elm.clientWidth;
            if( lastWidth != newWidth )
                callback(newWidth)
            lastWidth = newWidth

            if( elm.onElementHeightChangeTimer )
            clearTimeout(elm.onElementHeightChangeTimer)

            elm.onElementHeightChangeTimer = setTimeout(run, 200)
        })()
    }


    onElementHeightChange(document.body, function(width){
        if(showMenu == true && width>768){
            showMenu = false;
        }
    });

</script>

<style>
        header{
            display: flex;
            flex-direction: row;
            justify-content: space-around;
            align-items: center;
            box-sizing:border-box;

            width: 100%;
            max-width: 1920px;
        }

        nav{
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: flex-end;
            padding: 20px 50px;
            padding-right: 0;
        }

        .nav__icon{
            display: none;
            align-items: center;
            justify-content: center;
            cursor: pointer;
        }

        .nav__icon p{
            color: var(--color-white);
            font-family: var(--font-nunito);
            font-weight: bolder;
            margin-right: 10px;
            font-size: 18px;
            padding-top:4px;
        }

        .nav__items a{
            color: var(--color-white);        
            letter-spacing: 1px;
            text-decoration: none;
            font-family: var(--font-open);
            padding: 0 50px;
            box-sizing: border-box;
            transition: all .4s;
        }

        .nav__items a:hover{
           
            font-weight: bold;
            letter-spacing: 2px;
        }

        .Redes {
            display: flex;
            justify-content: center;
            align-items: center;
        }

        @media only screen and (max-width: 768px) {

            header{
                justify-content: space-between;
            }

            .header__blank{
                display: none;
            }

            .nav__icon{
                display: flex;
            }

            .nav__items{
                display: none;
            }
        }

        @media only screen and (min-width:768px) and (max-width: 835px){
            .nav__items a{
                padding: 0 35px;
            }
        }

        .header{
            width: 100vw;
            height: 100vh;

            position: fixed;
            top: 0;
            z-index: 20;

            display: flex;
            flex-wrap: nowrap;
            flex-direction: row;

            overflow: hidden;
        }

        .header__content{
            width: 80%;
            height: 100%;
            background: var(--color-white);

            padding: 20px 30px;
            padding-bottom: 80px;
            box-sizing: border-box;

            display:flex;
            flex-direction:column;
            justify-content: space-between;
            align-items: flex-start;
        }

        .header__content__items a{
            display: block;
            color: var(--color-black);
            text-decoration: none;

            font-weight: bolder;
            font-size: 28px;
            font-family: var(--font-open);

            opacity: 1;
            transition: all .4s;
        }

        .header__content__items__item:hover{
            color: var(--main-color);
            transform: translateX(15px);
        }

        .header__content__contact__correo{
            display: block;
            
            font-size: 20px;
            font-family: var(--font-open);
            font-weight: bolder;
            text-decoration: none;
            letter-spacing: .5px;
            color: var(--main-color) !important;
            
            margin-top: 0;
            transition: all .4s ease-in-out;
            
            border-bottom: solid 1px transparent;
        }

        .header__content__contact__number{
            font-weight: bolder;
            color: var(--color-black) !important;
            font-family: var(--font-open);
            font-size: 18px;
            margin: 0;
            transition: all .4s ease-in-out;
            text-decoration: none;
            border-bottom: solid 1px transparent;
            display: block;
        }
        
        .header__content__contact__city{
            color: var(--color-black) !important;
            margin-top: 50px;
            font-weight: normal;
            transition: all .4s ease-in-out;
            text-decoration: none;
            border-bottom: solid 1px transparent;
            display: block;
            font-family: var(--font-open);
        }

        .header__close{
            width:20%;
            height: 100%;
            background-color: var(--main-color);
            background-image: url("/images/fondoMenu.svg");
            background-size: cover;

            padding-top: 80px;
            display: flex;
            justify-content: center;
        }
    .header-color {
        padding: 10px 20px;
        box-sizing: border-box;
    }

    .header-color .nav__items a, .header-color .nav__icon p {
        color: var(--main-color);
    }

         
</style>

<header class="{origin !== "index" ? "header-color" : ""}">
        <div class="Logo"> {#if origin !== "index"}<Logo />{/if} </div>
        <nav>
            <div class="nav__icon" on:click="{ () => toggleMenu(true) }"> <p>Menú</p> <Bars colorBars={ origin === "index" ? "white" : "" } /></div>

            <div class="nav__items" class:showMenuItems="{showMenu === true}">
                <a rel="prefetch" href="/aboutme"> SOBRE MÍ </a>
                <a rel="prefetch" href="/portfolio"> PORTAFOLIO </a>
                <a rel="prefetch" href="/contact"> CONTACTO </a>
            </div>
        </nav>
        <div class="header__blank"></div>
</header>

{#if showMenu}
    <header class="header" in:slide="{{ duration: 600 }}" out:slide="{{ duration:600, delay: 100}}">
        <article class="header__content">
            
            <div class="header__content__logo" in:fly="{{y: -200, duration: 800}}">
                <Logo />
            </div>

            <div class="header__content__items">
                <a rel="prefetch" in:fly="{{x: -200, duration: 800, delay:400}}" out:fade href="/" class="header__content__items__item"> INICIO </a>
                <a rel="prefetch" in:fly="{{x: -200, duration: 800, delay:600}}" out:fade href="/aboutme" style="animation-delay:.2s" class="header__content__items__item"> SOBRE MÍ </a>
                <a rel="prefetch" in:fly="{{x: -200, duration: 800, delay:800}}" out:fade href="/portfolio" style="animation-delay:.4s" class="header__content__items__item"> PORTAFOLIO </a>
                <a rel="prefetch" in:fly="{{x: -200, duration: 800, delay:1000}}" out:fade href="/contact" style="animation-delay:.6s" class="header__content__items__item"> CONTACTO </a>
            </div>


            <div class="header__content__contact">
                <div in:fly="{{x: -200, duration: 800, delay:800}}" class="Redes">
                    {#each Redes as item}
                        <Icono name = { item.name } url = { item.url } image = { item.image } />
                    {/each}
                </div>
                <a rel="noopener" in:fly="{{x: -200, duration: 800, delay:800}}" out:fade target="_blank" href="https://goo.gl/maps/rRYB19Qf8SKHZFew7" class ="header__content__contact__city">CALI, COLOMBIA</a>                
                <a rel="noopener" in:fly="{{x: -200, duration: 800, delay:1000}}" out:fade target="_blank" href="https://api.whatsapp.com/send?phone=573162580525" class="header__content__contact__correo">+57 316 258 0525</a>
                <a rel="noopener" in:fly="{{x: -200, duration: 800, delay:1200}}" out:fade target="_blank" href="mailto:burbanojaime98@gmail.com?cc=otradir@correo.es&subject=www.jaimeburbano.com" class="header__content__contact__number">burbanojaime98@gmail.com</a>
            </div>

        </article>
        <article class="header__close">
            <div class="header__close__btn" on:click="{ () => toggleMenu(false) }" in:fly="{{y: -200, duration: 800}}">
                <CloseHeader />
            </div>
        </article>
    </header>
{/if}