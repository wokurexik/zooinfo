<script setup>
  const route = useRoute()
  const {slug} = useRoute().params
</script>

<template>
  <div>
    <BlogPage :path="`/posts/vysocina/zoo-jihlava/${slug}`"/>
  </div>
</template>

