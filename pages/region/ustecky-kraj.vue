<template>

      

    <Navbar 
    intent="primary"
    nav="none"
    />
    <div>
        <h1 class="text-center font-extrabold text-5xl mb-11 mt-11">Ústecký kraj</h1>
    </div>
    <div class="map w-[500px]">
        <img class="w-[500px]" src="../../assets/regions/ustecky.svg" alt="">
        
        <div class="point rounded-lg has-tooltip top-[200px] left-[300px]">
            <NuxtLink href="../usti-nad-labem" >
                <div class="arrow"></div>
                <p class="font-bold mt-2 px-5 text-white">Zoo Ústí nad Labem</p>
                <div class="rounded-bl-lg rounded-br-lg tooltip">
                    <p class="text-[15px] mt-3">Hodnocení</p>
                    <p class="text-[15px]">4.3⭐</p>
                </div>
            </NuxtLink>
        </div>
        <div class="point rounded-lg has-tooltip top-[300px] left-[200px]">
            <NuxtLink href="../zoopark-chomutov" >
                <div class="arrow"></div>
                <p class="font-bold mt-2 px-5 text-white text-center">Zoopark Chomutov</p>
                <div class="rounded-bl-lg rounded-br-lg tooltip">
                    <p class="text-[15px] mt-3">Hodnocení</p>
                    <p class="text-[15px]">4.4⭐</p>
                </div>
            </NuxtLink>
        </div>
    </div>

    <div class="text-3xl font-bold text-center mt-[100px]">
        <h2>Novinky z Ústeckého kraje</h2>
    </div>
    <div class=" mt-11">
        <!-- <BlogPostLatest :path="'/c'"/> -->
        <h2 class="text-center">Ještě nebyli přidány žádný příspěvky</h2>
    </div>  





</template>

<style scoped>


.map {
position:relative;
margin: 0 auto;
}
.point{
width: 200px;
height: 40px;
/* border-radius: 20PX; */
position:absolute;

align-items: center;
justify-content: center;
background-color:#006833;
}
.tooltip {
width: 200px;
color: white;
padding-inline: 10px !important;
padding: 10px 0px 10px 0px;
white-space: nowrap;
height: auto;
background-color:#006833;
}


</style> 