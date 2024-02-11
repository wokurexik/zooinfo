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