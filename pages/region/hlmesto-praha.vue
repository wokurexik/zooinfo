<template>

    <Navbar 
        intent="primary"
        nav="region"
        />
    <div>
        <h1 class="text-center font-extrabold text-5xl mb-11 mt-11">Hl. město Praha </h1>
    </div>
    <div class="map sm:w-[300px] lg:w-[500px]">
        <img class="sm:mt-[50px] sm:w-[300px] lg:w-[500px]" src="../../assets/regions/Praha.svg" alt="">

        <div class="point rounded-lg has-tooltip sm:top-[100px] sm:left-[200px] lg:top-[100px] lg:left-[300px]">
            <NuxtLink href="../zoo-praha" >
                <div class="arrow"></div>
                <p class="font-bold mt-[10px] sm:text-[13px] sm:px-2 lg:px-5 text-white">Zoo Praha</p>
                <div class="rounded-bl-lg rounded-br-lg tooltip">
                    <p class="text-[15px] mt-3">Hodnocení</p>
                    <p class="text-[15px]">4.4⭐</p>
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
width: 150px;
height: 40px;
/* border-radius: 20PX; */
position:absolute;

align-items: center;
justify-content: center;
background-color:#006833;
}
.tooltip {
width: 150px;
color: white;
padding-inline: 10px !important;
padding: 10px 0px 10px 0px;
white-space: nowrap;
height: auto;
background-color:#006833;
}

@media  only screen and (max-width: 768px  ) {

    .point{
    width: 100px;
    height: 40px;
    /* border-radius: 20PX; */
    position:absolute;

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