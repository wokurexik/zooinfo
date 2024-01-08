
<template>
    <div :class="backgroundClass" class="nav-img">
      <Navbar 
      btn="white"
      nav="homepage">
    </Navbar>
    <div class="lg:flex lg:gap-[0Px] sm:grid lg:mt-[150Px] sm:mt-[20Px] lg:h-[500px] lg:align-middle lg:justify-center">
      <div class="lg:mt-11 lg:text-5xl sm:text-4xl font-extrabold ml-5 ">
        <h1 class="lg:w-[650Px] sm:leading-[50px] lg:leading-[65px] sm:w-[400Px] text-white mb-8"> Prozkoumejte <span class="text-[--primary]">{{ dynamicText }}</span> <br> po celé České Republice </h1>
        <h2 class="font-bold text-white">Kam jedete<span class="text-[--primary]">?</span></h2>
      </div>
      <Map/>
    </div>
  </div>
  <!-- <ZooTypes/> -->

<TheMostVisited/>

</template>

<script>
export default {
  data() {
    return {
      dynamicText: "ZOO",
      textIndex: 0,
      currentBackgroundIndex: 0,
    };
  },
  computed: {
    backgroundClass() {
      return `background-${this.currentBackgroundIndex}`;
    },
  },
  mounted() {
    this.intervalIdText = setInterval(this.changeText, 5000);
    this.intervalIdBackground = setInterval(this.changeBackgroundImage, 5000);
  },
  beforeDestroy() {
    clearInterval(this.intervalIdText);
    clearInterval(this.intervalIdBackground);
  },
  methods: {
    changeText() {
      const texts = ["ZOO", "MINIZOO", "ZOOPARKY"];
      this.dynamicText = texts[this.textIndex];
      this.textIndex = (this.textIndex + 1) % texts.length;
    },
    changeBackgroundImage() {
      this.currentBackgroundIndex = (this.currentBackgroundIndex + 1) % 3;
    },
  },
};
</script>

<style scoped>
.nav-img {
  width: 100vw;
  background-size: cover;
  background-position: center;
  transition: background-image 1s ease-in-out;
}

@media (min-width: 400px) { 
  .nav-img {
    width: 100vw;
    height: 800px;
    background-size: cover;
    background-position: center;
    transition: background-image 1s ease-in-out;
  }

}
  

.nav-img {
  width: 100vw;
  background-size: cover;
  background-position: center;
  transition: background-image 1s ease-in-out;
}

.background-0 {
  background-image: url('~/assets/images/nav-img.png');
}

.background-1 {
  background-image: url('~/assets/images/landscape.png');
}

.background-2 {
  background-image: url('~/assets/images/nav-img.png');
}
</style>