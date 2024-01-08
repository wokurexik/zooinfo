<template>
   <div class="mt-[300px] ">
    <h2 class="text-4xl w-[1475px] underline mx-auto mb-10 font-bold">NEJNAVŠTĚVOVANĚJŠÍ</h2>
       <div class="flex">
           <div class="mb-[300px] gap-[25px]  mx-auto flex ]">
                <div v-for="zoo in mostViewedZoo" :key="zoo.id" class="w-[600Px] relative">
                    <a :href="zoo.path">
                        <img v-for="(img, index) in zoo.images.slice(0, 1)" :key="index" class="h-[420px] object-cover rounded-3xl absolute brightness-50 hover:brightness-100" :src="img" alt="">
                        <p class="absolute inset-0 flex items-center justify-center px-[50px] text-center text-white font-extrabold text-6xl">{{ zoo.title }}</p>
                    </a>
                </div>

               <div class="grid justify-content gap-2">
                    <div class="flex gap-6 flex-wrap w-[850px]">
                        <div v-for="zoo in sortedZoos" :key="zoo.id" class="w-[400Px] h-[200px] relative">
                            <a :href="zoo.path" >
                                <img v-for="(img, index) in zoo.images.slice(0, 1)" :key="index" class="w-[400px] brightness-50 rounded-3xl absolute h-[200px] object-cover" :src="img" alt="">
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