<template>
  <Navbar nav="none"/>
    <div class=" px-4 mx-auto">
  
      <header class="mt-8 mb-4 text-center justify-between items-end">
        <div class="">
          <h1 class="text-xl font-semibold">
            <NuxtLink to="/blog">Personal Blog</NuxtLink>
          </h1>
          <p class="text-gray-500">Learn programming easily</p>
        </div>
        <div class="justify-center flex mt-5">
          <div class="flex w-[1500px]  region-links justify-evenly flex-wrap gap-5 mt-5 p-5 bg-gray-100 shadow-sm rounded-xl ">
            
            <NuxtLink to="/blog/">
              <Btn>Středočeský</Btn>
            </NuxtLink>
            <NuxtLink to="/blog/">
              <Btn>Hl. město Praha</Btn>
            </NuxtLink>
            <NuxtLink to="/blog/">
              <Btn>Jihočeský</Btn>
            </NuxtLink>
            <NuxtLink to="/blog/">
              <Btn>Plzeňský</Btn>
            </NuxtLink>
            <NuxtLink to="/blog/">
              <Btn>Karlovarský</Btn>
            </NuxtLink>
            <NuxtLink to="/blog/">
              <Btn>Ústecký</Btn>
            </NuxtLink>
            <NuxtLink to="/blog/">
              <Btn>Liberecký </Btn>
            </NuxtLink>
            <NuxtLink to="/blog/">
              <Btn>Královéhradecký </Btn>
          </NuxtLink>
          <NuxtLink to="/blog/">
            <Btn>Pardubický</Btn>
          </NuxtLink>
          <NuxtLink to="/blog/vysocina">
            <Btn>Vysočina</Btn>
          </NuxtLink>
          <NuxtLink to="/blog/jihomoravsky">
            <Btn>Jihomoravský</Btn>
          </NuxtLink>
          <NuxtLink to="/blog/">
            <Btn>Olomoucký</Btn>
          </NuxtLink>
          <NuxtLink to="/blog/">
            <Btn>Moravskoslezský</Btn>
          </NuxtLink>
          <NuxtLink to="/blog/">
            <Btn>Zlínský</Btn>
          </NuxtLink>
        </div>
      </div>
      </header>
      
      <slot/>
      
    </div>
  </template>

<style>



.region-links > a:hover {
  text-decoration: underline;
}
</style>