<script setup>
  const route = useRoute()
  const {slug} = useRoute().params
</script>

<template>
  <div>
    <BlogPage :path="`/posts/jihomoravsky-kraj/zoo-brno/${slug}`"/>
  </div>
</template>

