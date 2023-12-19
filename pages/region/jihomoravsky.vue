<template>
    <div class="container ">

        <div class="map w-[500px]">
            <img src="../../assets/regions/jihomoravsky.svg" alt="">

            <div class="point rounded-lg has-tooltip top-[100px] left-[300px]">
                <NuxtLink href="../zoo/brno" >
                    <div class="arrow"></div>
                    <p class="font-bold mt-2 px-5 text-white">MiniZoo Kokot</p>
                    <div class="rounded-bl-lg rounded-br-lg tooltip">
                        <p class="text-[15px] mt-3">Hodnocení</p>
                        <img src="../../assets/regions/stars/four.svg" alt="">
                    </div>
                </NuxtLink>
            </div>
            <div class="point rounded-lg has-tooltip top-[200px] left-[100px]">
                <NuxtLink href="../zoo/brno" >
                    <div class="arrow"></div>
                    <p class="font-bold mt-2 px-5 text-white">MiniZoo Kokot</p>
                    <div class="rounded-bl-lg rounded-br-lg tooltip">
                        <p class="text-[15px] mt-3">Hodnocení</p>
                        <img src="../../assets/regions/stars/four.svg" alt="">
                    </div>
                </NuxtLink>
            </div>
        </div>
        
    </div>
    


</template>

<style scoped>


.arrow {
    width: 0px;
   height: 0px;
   border-style: solid;
   border-width: 0 20px 40px 20px;
   border-color: transparent transparent #006833 transparent;
   transform: rotate(270deg);
   right: 147px;
   position: absolute;
}

.map {
    position:relative;
    margin: 0 auto;
}
.point{
    width: auto;
    height: 40px;
    /* border-radius: 20PX; */
    position:absolute;
    
    align-items: center;
    justify-content: center;
    background-color:#006833;
}
.tooltip {
    width: auto;
    color: white;
    padding-inline: 10px !important;
    padding: 10px 0px 10px 0px;
    white-space: nowrap;
    height: auto;
    background-color:#006833;
}


 </style> 