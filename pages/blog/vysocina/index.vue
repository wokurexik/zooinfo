<template>
    <NuxtLayout name="blog">   
    <BlogFilterBtn/>
    <div class="h-1 bg-gray-300"></div>
       <div class=" mt-11 justify-center mb-11 flex-wrap bg-gray-200 gap-5 flex rounded-lg ">
           <div v-for="item in zoo" :key="item.name" class="py-2 justify-center text-center flex rounded-lg">
            <a class="py-3 px-5 rounded-lg text-sm font-semibold hover:underline ">
                <a :href="item.href" :class="item.class">
                    {{ item.name }}
                </a>
            </a>
                <p class="mt-1 text-gray-600">{{ item.description }}</p>
            </div>
        </div>
        <h1 class="text-3xl mb-11 text-center font-semibold">Novinky z kraje Vysočina</h1>
        <BlogPost :path="'/posts/vysocina'"/>
    </NuxtLayout>
</template>

<script setup>

    const zoo = [
      { name: 'Zoo Jihlava',  href: '/blog/vysocina/zoo-jihlava',  state: "notActive"},
      { name: 'Zoo Kokot',  href: '/blog/vysocina/zoo-jihlava',   state: "notActive"},
    ]


</script>