<template>
    <Navbar 
      intent="primary"
      nav="jihlava">
        Jihlava
    </Navbar>
    <section>
        <hr>
        <div class="flex gap-[50px] justify-center mt-[20px] mb-[100px]">
            <div class="flex gap-2">
                <div class="my-auto">
                    <img src="../../assets/icons/clock.svg" alt="">
                </div>
                <div class="text-center">
                    <p class="font-bold text-[20px]">Otevírací doba</p>
                    <small class="text-[17px]">9:00 - 16:00</small>
                </div>
            </div>
            <div class="flex gap-2">
                <div class="my-auto">
                    <img src="../../assets/icons/ticket.svg" alt="">
                </div>
                <div class="text-center">
                    <p class="font-bold text-[20px]">Vstupné</p>
                    <small class="text-[17px]">150 Kč / 100 Kč</small>
                </div>
            </div>
            <div class="flex gap-2">
                <div class="my-auto">
                    <img src="../../assets/icons/cloud.svg" alt="">
                </div>
                <div class="text-center">
                    <p class="font-bold text-[20px]">Počasí</p>
                    <small class="text-[17px]">1 °C</small>
                </div>
            </div>
        </div>
        <div class="mx-auto flex max-w-7xl gap-[200px]">
            <div class="">
                <h1 class="text-[30px] mb-3 font-bold">Úvod</h1>
                <p class=" mb-5 w-[600px]">V údolí říčky Jihlávky leží Zoo Jihlava, která je domovem více než 200 druhů zvířat. 
                    V posledních letech zoologická zahrada prochází velkým vývojem a postavila několik nových pavilonů. 
                    Zoo je známá tím, že chová perské levharty, které mají v České republice pouze v Zoo Dvůr Králové.</p>

                <a class="underline" href="">Webové stránky Zoologické zahrady Jihlava</a>

                <div class="mt-5">
                    <h2 class="text-[30px] font-bold">Hodnocení návštěvníků</h2>
                    <img class="w-[150px]" src="../../assets/regions/stars/four.svg" alt="">
                </div>
            </div>
            <div>
                <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d81866.24621303468!2d14.336171150207495!3d50.117730085983816!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x470bead4f9db039b%3A0x96d9543c02ebb5bd!2sZoo%20Praha!5e0!3m2!1scs!2scz!4v1702335949034!5m2!1scs!2scz" width="400" height="300" style="border:0;" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
            </div>
        </div>

        <div class="">
            
        </div>

    <div class="bg-white py-24 sm:py-32">
    <div class="mx-auto max-w-7xl px-6 lg:px-8">
      <div class="mx-auto max-w-2xl lg:mx-0">
        <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">From the blog</h2>
        <p class="mt-2 text-lg leading-8 text-gray-600">Learn how to grow your business with our expert advice.</p>
      </div>
      <div class="mx-auto mt-10 grid max-w-2xl grid-cols-1 gap-x-8 gap-y-16 border-t border-gray-200 pt-10 sm:mt-16 sm:pt-16 lg:mx-0 lg:max-w-none lg:grid-cols-3">
        <article v-for="post in posts" :key="post.id" class="flex max-w-xl flex-col items-start justify-between">
          <div class="flex items-center gap-x-4 text-xs">
            <time :datetime="post.datetime" class="text-gray-500">{{ post.date }}</time>
            <a :href="post.category.href" class="relative z-10 rounded-full bg-gray-50 px-3 py-1.5 font-medium text-gray-600 hover:bg-gray-100">{{ post.category.title }}</a>
          </div>
          <div class="group relative">
            <h3 class="mt-3 text-lg font-semibold leading-6 text-gray-900 group-hover:text-gray-600">
              <a :href="post.href">
                <span class="absolute inset-0" />
                {{ post.title }}
              </a>
            </h3>
            <p class="mt-5 line-clamp-3 text-sm leading-6 text-gray-600">{{ post.description }}</p>
          </div>
        </article>
      </div>
    </div>
  </div>


    </section>
</template>

<script setup>
import posts from '../../data/posts.json'


</script>