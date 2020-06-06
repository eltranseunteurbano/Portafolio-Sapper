<script>
    
    export let name
    export let url
    export let image
    export let type = "normal";

</script>

<style>

    .Icono, .Icono-footer {
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

    .Icono-footer span {
        display: none;
    }

    .Icono-footer a {
        background: var(--color-black);
        border: none
    }

</style>

<div class="{type === "footer" ? "Icono-footer" : "Icono" }">
    <a rel="noopener" href = { url } target="_blank">
        <img src = { type === "footer" ? image + "-Blanco.svg" : image + ".svg" } alt = { name }>
    </a>

     <span> { name } </span>
</div>