<script>
    
    export let name
    export let url
    export let image

</script>

<style>

    .Icono {
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;

        position: relative;
        cursor: pointer;

    }

    a{
        width: 30px;
        height: 30px;

        display: flex;
        justify-content: center;
        align-items: center;

        background: var(--color-white);
        border-radius: 30px;
        opacity: .4;
        transition: all .4s;

        margin: 5px;

        border: solid 1px var(--main-color)

    }

    a:hover {
        opacity: 1;
    }

    span {
        color: var(--color-white);
        font-family: var(--font-nunito);
        opacity: 0;
        transition: all .4s;
        position: absolute;
        bottom: -20px;
        width: max-content;

    }

    a:hover ~ span{
        opacity: .8;
    }

</style>

<div class="Icono">
    <a rel="noopener" href = { url } target="_blank">
        <img src = { image } alt = { name }>
    </a>

     <span> { name } </span>
</div>