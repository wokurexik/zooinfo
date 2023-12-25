<template>
    <NuxtLayout name="blog">
        <BlogFilterBtn />
        <h1 class="text-3xl mb-11 mt-11 text-center font-semibold">Všechny články</h1>
        <BlogPost :path="'/posts'"/>
    </NuxtLayout>
</template>

<script>
const regions = [
  { name: 'Středočesk',  href: '/blog/stredocesky-kraj',  },
  { name: 'Hl. město Praha',  href: '/blog/hlmesto-praha',  },
  { name: 'Jihočeský', href: '/blog/jihocesky-kraj',},
  { name: 'Plzeňský', href: '/blog/plzensky-kraj', },
  { name: 'Karlovarský', href: '/blog/kralovarsky-kraj', },
  { name: 'Ústecký', href: '/blog/ustecky-kraj', },
  { name: 'Liberecký',  href: '/blog/liberecky-kraj',  },
  { name: 'Královéhradecký', href: '/blog/kralovehradecky-kraj',},
  { name: 'Pardubický', href: '/blog/pardubicky-kraj', },
  { name: 'Vysočina', href: '/blog/vysocina', },
  { name: 'Jihomoravský', href: '/blog/jihomoravsky-kraj', },
  { name: 'Olomoucký', href: '/blog/olomoucky-kraj', },
  { name: 'Moravskoslezský', href: '/blog/moravskoslezsky-kraj', },
  { name: 'Zlínský', href: '/blog/zlinsky-kraj', },
]
</script>