<template>

        <Navbar 
            intent="primary"
            nav="region"
            />
        <div>
            <h1 class="text-center font-extrabold text-5xl mb-11 mt-11">Jihomoravský kraj</h1>
        </div>
        <div class="map sm:w-[300px] lg:w-[500px]">
            <img class="sm:mt-[50px] sm:w-[300px] lg:w-[500px]" src="../../assets/regions/jihomoravsky.svg" alt="">

            <div class="point rounded-lg has-tooltip sm:top-[150px] sm:left-[70px] lg:top-[250px] lg:left-[170px]">
                <NuxtLink href="../zoo-hodonin" >
                    <div class="arrow-right"></div>
                    <p class="font-bold  sm:text-[11px] md:text-[15px] px-5 text-white text-center">Zoo Hodonín</p>
                    <div class="rounded-bl-lg rounded-br-lg tooltip">
                        <p class="text-[15px] mt-3">Hodnocení</p>
                        <p class="text-[15px]">4.6⭐</p>
                    </div>
                </NuxtLink>
            </div>
            <div class="point rounded-lg has-tooltip sm:top-[100px] sm:left-[180px] lg:top-[140px] lg:left-[300px]">
                <NuxtLink href="../zoo-brno" >
                    <div class="arrow"></div>
                    <p class="font-bold sm:text-[11px] md:text-[15px] px-5 text-white text-center">Zoo Brno</p>
                    <div class="rounded-bl-lg rounded-br-lg tooltip">
                        <p class="text-[15px] mt-3">Hodnocení</p>
                        <p class="text-[15px]">4.6⭐</p>
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
align-items: center;
justify-content: center;
display: flex;
background-color:#006833;
}

.tooltip {
box-shadow: 1px 10px 10px #004b24;
border-top: none;
width: 180px;
color: white;
padding-inline: 10px !important;
padding: 10px 0px 10px 0px;
left: 0px;
white-space: nowrap;

height: auto;
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