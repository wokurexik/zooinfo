<template>
  <Navbar nav="landscape"/>
    <div class="max-w-3xl px-4 mx-auto">
  
      <header class="mt-8 mb-4 flex justify-between items-end">
        <div>
          <h1 class="text-xl font-semibold">
            <NuxtLink to="/blog">Personal Blog</NuxtLink>
          </h1>
          <p class="text-gray-500">Learn programming easily</p>
        </div>
        <NuxtLink to="/blog/vysocina">
          <Btn>Jihlava</Btn>
        </NuxtLink>
        <NuxtLink to="/blog/jihomoravsky">
          <Btn>Praha</Btn>
        </NuxtLink>
      </header>
  
      <slot/>
  
    </div>
</template>