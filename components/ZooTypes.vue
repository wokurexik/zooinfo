<template>
    <div class="flex">
        <div class="background background-1">
            <h3 class=" text-5xl text-white font-extrabold ">ZOO</h3>
        </div>
        <div class="background background-2">
            <h3 class=" text-5xl text-white font-extrabold ">MINIZOO</h3>
        </div>
        <div class="background background-3">
            <h3 class=" text-5xl text-white font-extrabold ">ZOOPARKY</h3>
        </div>
    </div>
</template>

<style scoped>



.background {
    width: 100%;
    height: 150px;
    background-repeat: none !important;
    object-fit: cover !important;
    display: flex;
    align-items: center;
    justify-content: center;
}

.background-1 {
    background-image: url("../assets/images/zoo-jihlava.png");
}
.background-2 {
    background-image: url("../assets/images/zoo-brno.jpg");
}
.background-3 {
    background-image: url("../assets/images/zoo-praha.jpg");
}


</style>