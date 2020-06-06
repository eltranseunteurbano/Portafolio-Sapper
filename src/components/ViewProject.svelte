<style>

    .project {
        width: 300px;
        height: 300px;
        /*background-color: var(--color-white);*/
        background-color: pink;

        background-repeat: no-repeat;
        background-position: center;
        background-size: cover;

        box-shadow: var(--shadow);
        
        position: relative;
        cursor: pointer;
        transition: all .4s;
        border: solid 4px var(--color-white);

    }

    .project div {
        width: 100%;
        height: 100%;

        background-color: rgba(0, 0, 0, .5);
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        opacity: 0;
        transition: all .4s;
    }

    h4 {
        font-family: var(--font-open);
        color: var(--color-white);
        font-weight: bolder;
        font-size: 20px;
        margin-bottom: 10px;
    }

    p {
        font-family: var(--font-nunito);
        color: var(--color-white);
        font-weight: regular;
        font-size: 16px;
    }

    .project:hover {
        border: solid 4px var(--second-color);
        border-radius: 4px;
    }

    .project:hover div {
        opacity: 1;
    }


</style>

<div class="project">
    
    <div>
        <h4>NOMBRE</h4>
        <p>Categoría</p>
    </div>

</div>