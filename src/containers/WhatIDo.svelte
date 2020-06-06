<script>
    import { Profesion } from '../assets/scritps/DataObjects'
</script>

<style>

    .QueHago {
        
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        margin-bottom: 150px;

        max-width: 1500px;
    }

    img{
        margin-bottom: 30px;
    }

    .wrapper{
        width: 100%;
        display: grid;
        grid-template: repeat(auto) / 1fr;
        grid-gap: 40px;

        margin-bottom: 60px;
    }

    .item {
        width: 100%;
        padding: 20px;
        box-sizing: border-box;
        
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
    }

    .item h2 {
        color: var(--color-black);
        font-family: var(--font-open);
        font-weight: bolder;
        text-align: center;
        font-size: 18px;
        margin-bottom: 20px;
    }

    .item p {
        color: var(--color-black);
        font-family: var(--font-nunito);
        max-width: 650px;
        text-align: center;
        font-size: 18px;
        line-height: 25px;
    }

@media only screen and (min-width: 768px) {
    .wrapper {
        grid-template: 1fr / 1fr 1fr 1fr;
    }
}
    

</style>

<section class="QueHago">  

    <h1 class="title">¿Que puedo hacer?</h1>

    <article class="wrapper">

        { #each Profesion as item }
            <div class="item">
            <img src={ item.img } alt={item.title} />
                <h2>{item.title}</h2>
                <p>{item.text}</p>
            </div>
        { /each }

    </article>

    <a class="button" href="/aboutme">A CERCA DE MÍ</a>
</section>