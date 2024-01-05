<template>

        <Navbar 
            intent="primary"
            nav="none"
            />
        <div>
            <h1 class="text-center font-extrabold text-5xl mb-11 mt-11">Karlovarský kraj</h1>
        </div>
        <div class="map w-[500px]">
            <img class="w-[500px]" src="../../assets/regions/karlovarsky.svg" alt="">

            <div class="point rounded-lg has-tooltip top-[100px] left-[300px]">
                <NuxtLink href="" >
                    <div class="arrow"></div>
                    <p class="font-bold mt-2 px-5 text-white"></p>
                    <div class="rounded-bl-lg rounded-br-lg tooltip">
                        <p class="text-[15px] mt-3">Hodnocení</p>
                        <img src="../../assets/regions/stars/four.svg" alt="">
                    </div>
                </NuxtLink>
            </div>
            <div class="point rounded-lg has-tooltip top-[200px] left-[100px]">
                <NuxtLink href="" >
                    <div class="arrow"></div>
                    <p class="font-bold mt-2 px-5 text-white"></p>
                    <div class="rounded-bl-lg rounded-br-lg tooltip">
                        <p class="text-[15px] mt-3">Hodnocení</p>
                        <img src="../../assets/regions/stars/four.svg" alt="">
                    </div>
                </NuxtLink>
            </div>
        </div>
        
    


</template>

<style scoped>


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