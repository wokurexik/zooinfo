<template>

    <Navbar 
        intent="primary"
        nav="region"
        />
    <div>
        <h1 class="text-center font-extrabold text-5xl mb-11 mt-11">Jihočeský kraj</h1>
    </div>
    <div class="map sm:w-[300px] lg:w-[500px]">
        <img class="sm:mt-[50px] sm:w-[300px] lg:w-[500px]" src="../../assets/regions/jihocesky.svg" alt="">

            <div class="point rounded-lg has-tooltip sm:top-[140px] sm:left-[-10px] lg:top-[200px] lg:left-[40px]">
                <NuxtLink href="../zoo-hluboka" >
                    <div class="arrow-right"></div>
                    <p class="font-bold  md:text-[15px] sm:text-[11px] px-5 text-white text-center">Zoo Hluboká</p>
                    <div class="rounded-bl-lg rounded-br-lg tooltip">
                        <p class="text-[15px] mt-3">Hodnocení</p>
                        <p class="text-[15px]">4.6⭐</p>
                    </div>
                </NuxtLink>
            </div>
            <div class="point rounded-lg has-tooltip sm:top-[180px] sm:left-[190px] lg:top-[250px] lg:left-[310px]">
                <NuxtLink href="../zoo-dvorec" >
                    <div class="arrow"></div>
                    <p class="font-bold  sm:text-[11px] md:text-[15px] px-5 text-white text-center">Zoo Dvorec</p>
                    <div class="rounded-bl-lg rounded-br-lg tooltip">
                        <p class="text-[15px] mt-3">Hodnocení</p>
                        <p class="text-[15px]">4.5⭐</p>
                    </div>
                </NuxtLink>
            </div>
            <div class="point rounded-lg has-tooltip  sm:top-[90px] sm:left-[60px] lg:top-[185px] lg:left-[384px]">
                <NuxtLink href="../zoo-na-hradecku" >
                    <div class="sm:hidden arrow"></div>
                    <div class="md:hidden arrow-right"></div>
                    <p class="font-bold px-5 sm:text-[11px] text-white md:text-[15px] text-center">Zoo na Hrádečku</p>
                    <div class="rounded-bl-lg rounded-br-lg tooltip">
                        <small class="text-[15px] mt-3">Hodnocení</small>
                        <p class="text-[15px]">4.7⭐</p>
                    </div>
                </NuxtLink>
            </div>
            <div class="point rounded-lg has-tooltip  sm:top-[30px] sm:left-[200px] lg:top-[50px] lg:left-[310px]">
                <NuxtLink href="../zoo-tabor" >
                    <div class="arrow"></div>
                    <p class="font-bold  px-5 sm:text-[11px] md:text-[15px] text-white text-center">Zoo Tábor</p>
                    <div class="rounded-bl-lg rounded-br-lg tooltip">
                        <small class="text-[15px] mt-3">Hodnocení</small>
                        <p class="text-[15px]">4.2⭐</p>
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
width: 180px;
height: 40px;
/* border-radius: 20PX; */
position:absolute;
display: flex;
align-items: center;
justify-content: center;
background-color:#006833;
}

.tooltip {
box-shadow: 1px 10px 10px #004b24;
border-top: none;
width: 180px;
color: white;
padding-inline: 10px !important;
padding: 10px 0px 10px 0px;
white-space: nowrap;
height: auto;
left: 0px;
background-color:#006833;
}

@media  only screen and (max-width: 768px  ) {

.point{
width: 120px;
height: 36px;
/* border-radius: 20PX; */
position:absolute;
display: flex;
align-items: center;
justify-content: center;
background-color:#006833;
}
.tooltip {
width: 40px;
display: none;
color: white;
padding-inline: 10px !important;
padding: 10px 0px 10px 0px;
white-space: nowrap;
height: auto;
background-color:#006833;
}

}



</style> 