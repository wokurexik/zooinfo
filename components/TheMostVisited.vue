<template>
   <div class="mt-[300px] ">
    <h2 class="text-4xl lg:w-[1475px] sm:text-center underline mx-auto mb-10 font-bold">NEJNAVŠTĚVOVANĚJŠÍ</h2>
       <div class="flex sm:justify-center">
           <div class="lg:mb-[300px] sm:gap-[25px] lg:gap-[25px] sm:grid lg:mx-auto lg:flex ]">
                <div v-for="zoo in mostViewedZoo" :key="zoo.id" class="lg:w-[600Px] lg:h-[420px] sm:h-[100px] relative">
                    <a :href="zoo.path">
                        <img v-for="(img, index) in zoo.images.slice(0, 1)" :key="index" class=" sm:rounded-none lg:h-[420px] lg:w-[600px] sm:w-[400px] sm:h-[100px] object-cover lg:rounded-3xl absolute brightness-50 hover:brightness-100" :src="img" alt="">
                        <p class="absolute inset-0 flex items-center justify-center px-[50px] text-center text-white font-extrabold sm:text-3xl lg:text-6xl">{{ zoo.title }}</p>
                    </a>
                </div>

               <div class="grid justify-content gap-2">
                    <div class="flex gap-6 sm:w-[400Px] flex-wrap lg:w-[850px]">
                        <div v-for="zoo in sortedZoos" :key="zoo.id" class="sm:w-[400Px] sm:h-[100px] lg:h-[200px] relative">
                            <a :href="zoo.path" >
                                <img v-for="(img, index) in zoo.images.slice(0, 1)" :key="index" class="sm:rounded-none sm:w-[400px] brightness-50 lg:rounded-3xl absolute sm:h-[100Px] lg:h-[200px] object-cover" :src="img" alt="">
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
      this.sortedZoos = zoosWithReviewStars.slice(1, 5);
      this.mostViewedZoo = [zoosWithReviewStars[0]];

      console.log('Top Zoos:', this.sortedZoos.map(zoo => zoo.title));
    },
  },
};
</script>