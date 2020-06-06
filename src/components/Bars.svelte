<script>

    export let colorBars;

</script>

<style>

.icon{
        cursor: pointer;
        transition: all .4s;
        transform:rotate(90deg);
    }

.lineOne{
        d:path("M21 21 L21 9");
        transition: all .4s;
        stroke: #e94368;
    }

    .lineTwo{
        d:path("M15 21 L15 9");
        transition: all .4s;
        stroke: #e94368;
    }

    .lineThree{
        d:path("M9 9 L9 21");
        transition: all .4s;
        stroke: #e94368;
    }

    .white{
        stroke: white;
    }
        
</style>

<svg class="icon" width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path class="lineOne" d="" class:white="{ colorBars === "white"}" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
    <path class="lineTwo" d="" class:white="{ colorBars === "white"}" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
    <path class="lineThree" d="" class:white="{ colorBars === "white"}" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
</svg>