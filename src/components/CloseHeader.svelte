<style>
    .close{
        cursor: pointer;
        transition: all .4s;
        transform: rotate(0);
    }

    .close:hover{
        transform:rotate(90deg);
    }

    .lineOne{
        transition: all .4s;
        d:path("M21 9 L9 21");
    }

    .lineTwo{
        transition: all .4s;
        d:path("M9 9 L21 21");
    }

    .lineThree{
        transition: all .4s;
        d:path("M9 9 L9 9");
    }
        
    .close:hover .lineOne{
        d:path("M21 21 L21 9");
    }
        
    .close:hover .lineTwo{
        d:path("M15 21 L15 9");
    }
        
    .close:hover .lineThree{
        d:path("M9 9 L9 21");
        }
    </style>

<svg class="close" width="30" height="30" viewBox="0 0 30 30" fill="none" xmlns="http://www.w3.org/2000/svg">
    <circle cx="15" cy="15" r="15" fill="white"/>
    <path class="lineOne" d="" stroke="#E94368" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
    <path class="lineTwo" d="" stroke="#E94368" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
    <path class="lineThree" d="" stroke="#E94368" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
</svg>