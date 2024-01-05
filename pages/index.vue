
<template>
    <div :class="backgroundClass" class="nav-img">
      <Navbar 
      btn="white"
      nav="homepage">
    </Navbar>
    <div class="flex gap-[0Px]  mt-[150Px] h-[500px] align-middle justify-center">
      <div class="mt-11 text-5xl font-extrabold ml-11 ">
        <h1 class="w-[650Px] leading-[65px] text-white mb-8"> Prozkoumejte <span class="text-[--primary]">{{ dynamicText }}</span> <br> po celé České Republice </h1>
        <h2 class="font-bold text-white">Kam jedete<span class="text-[--primary]">?</span></h2>
      </div>
      <Map/>
    </div>
  </div>
  <ZooTypes/>

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