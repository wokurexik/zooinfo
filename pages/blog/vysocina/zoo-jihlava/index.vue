<template>
   <NuxtLayout name="blog">
    <BlogFilterBtn/>
    <h1 class="text-3xl mt-11 mb-11 text-center font-semibold">Novinky ze Zoo Jihlava</h1>
        <BlogPost :path="'/posts/vysocina/zoo-jihlava'"/>
    </NuxtLayout>
</template>

