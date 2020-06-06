<script>
    import Logo from './Logo'
    import Bars from './Bars'
</script>

<style>

    header {
        width: 100%;

        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
    }

    .Logo{
        opacity: 0;
    }

    .nav__items {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .nav__items p {
        color: var(--color-white);
        font-family: var(--font-nunito);
        margin-right: 5px;
        font-size: 18px;
        padding-top: 2px
    }

</style>

<header>
    <div class="Logo">
        <Logo />
    </div>

    <nav>
        <div class="nav__items"> <p>Menú </p> <span><Bars colorBars="white" /> </span></div>
    </nav>

</header>