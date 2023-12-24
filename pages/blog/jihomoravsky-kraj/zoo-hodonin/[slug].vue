<script setup>
  const route = useRoute()
  const {slug} = useRoute().params
</script>

<template>
  <div>
    <BlogPage :path="`/posts/jihomoravsky-kraj/zoo-hodonin/${slug}`"/>
  </div>
</template>

