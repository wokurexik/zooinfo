<template>
   <div class="sm:mt-[150px] lg:mt-[300px] overflow-hidden ">
    <h2 class="lg:text-4xl md:text-3xl sm:text-2xl lg:w-[1475px] sm:text-center mx-auto mb-10 font-bold">NEJNAVŠTĚVOVANĚJŠÍ</h2>
       <div class=" flex sm:justify-center">
           <div class="lg:mb-[300px] sm:gap-[25px] lg:gap-[25px] sm:grid lg:mx-auto lg:flex md:w-[800px] lg:w-[auto] sm:w-[350Px] sm:justify-center">
                <div v-for="zoo in mostViewedZoo" :key="zoo.id" class="lg:w-[600Px] lg:h-[420px] md:h-[200px] sm:h-[100px] md:w-[720px] relative md:mx-auto">
                    <a :href="zoo.path">
                        <img v-for="(img, index) in zoo.images.slice(0, 1)" :key="index" class=" sm:rounded-none lg:h-[420px] lg:w-[600px] md:h-[200px] md:w-[720px] sm:w-full sm:px-3  sm:h-[200px] object-cover absolute brightness-50" :src="img" alt="">
                        <p class="absolute inset-0 flex items-center justify-center px-[50px] md:my-[100px] sm:my-[100px] text-center md:w-[700px] text-white font-extrabold md:text-6xl sm:text-3xl lg:text-6xl">{{ zoo.title }}</p>
                    </a>
                </div>

               <div class="grid gap-2">
                    <div class="flex md:mt-[0px] lg:mt-0 sm:mt-[100px] gap-6 sm:w-[400Px] sm:justify-center flex-wrap md:w-[850px] lg:w-[730px]">
                        <div v-for="zoo in sortedZoos" :key="zoo.id" class="sm:w-[350Px] sm:h-[100px] lg:h-[200px] relative ">
                            <a :href="zoo.path" >
                                <img v-for="(img, index) in zoo.images.slice(0, 1)" :key="index" class="sm:rounded-none  sm:w-[350px] brightness-50 absolute sm:h-[100Px] lg:h-[200px] object-cover" :src="img" alt="">
                                <p class="absolute inset-0 flex px-[50px] items-center justify-center text-white font-extrabold text-3xl text-center">{{ zoo.title }}</p>
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script >
import zoosData from '../../zoo.json';

export default {
  data() {
    return {
      sortedZoos: [],
      mostViewedZoo: [],
    };
  },
  mounted() {
    this.sortZoosByReviewStars();
  },
  methods: {
    sortZoosByReviewStars() {
      // Convert object to array
      const zoosArray = Object.values(zoosData);

      // Filter out zoos without reviewStars
      const zoosWithReviewStars = zoosArray.filter(zoo => zoo.reviewStars !== undefined);

      // Sort zoos by reviewStars in descending order
      zoosWithReviewStars.sort((a, b) => {
        const starsA = parseFloat(a.reviewStars.replace(',', '.')) || 0; // Use 0 as a fallback
        const starsB = parseFloat(b.reviewStars.replace(',', '.')) || 0; // Use 0 as a fallback
        return starsB - starsA;
      });

      console.log('Sorted Zoos:', zoosWithReviewStars.map(zoo => zoo.title));

      // Take the top 5 zoos

      
      if (window.innerWidth > 1024) {
        this.sortedZoos = zoosWithReviewStars.slice(1, 5);
        this.mostViewedZoo = [zoosWithReviewStars[0]];
      } else{
        this.sortedZoos = zoosWithReviewStars.slice(1, 3);
        this.mostViewedZoo = [zoosWithReviewStars[0]];
      }


      console.log('Top Zoos:', this.sortedZoos.map(zoo => zoo.title));
    },
  },
};
</script>