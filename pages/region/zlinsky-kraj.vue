<template>

    <Navbar 
        intent="primary"
        nav="none"
        />
    <div>
        <h1 class="text-center font-extrabold text-5xl mb-11 mt-11">Zlínský kraj</h1>
    </div>
    <div class="map w-[500px]">
        <img class="w-[500px]" src="../../assets/regions/zlinsky.svg" alt="">

        <div class="point rounded-lg has-tooltip top-[100px] left-[300px]">
            <NuxtLink href="../zoo/zoo-brno" >
                <div class="arrow"></div>
                <p class="font-bold mt-2 px-5 text-white text-center">Zoo Zlín</p>
                <div class="rounded-bl-lg rounded-br-lg tooltip">
                    <p class="text-[15px] mt-3">Hodnocení</p>
                    <img src="../../assets/regions/stars/four.svg" alt="">
                </div>
            </NuxtLink>
        </div>
    </div>
    



</template>
