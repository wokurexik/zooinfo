<template>
    <NuxtLayout name="blog">
     <BlogFilterBtn/>
     <h1 class="text-3xl mt-11 mb-11 text-center font-semibold">Novinky ze Zoo Brno</h1>
         <BlogPost :path="'/posts/jihomoravsky-kraj/zoo-brno'"/>
     </NuxtLayout>
 </template>
 
 