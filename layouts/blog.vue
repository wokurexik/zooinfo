<template>
  <Navbar nav="none"/>
    <div class=" px-4 mx-auto">
  
      <header class="mt-8 mb-4 text-center justify-between items-end">
        <div class="">
          <h1 class="text-xl font-semibold">
            <NuxtLink to="/blog">Všechny články</NuxtLink>
          </h1>
        </div>
      </header>
    </div>
    
  <slot/>
          
</template>
            


<style>

s:hover {
  color: white;
}

</style>

<style>



.region-links > a:hover {
  text-decoration: underline;
}
</style>