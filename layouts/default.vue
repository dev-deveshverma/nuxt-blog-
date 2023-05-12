<template>
  <div>
    <Navbar />
    <slot />
    <section-recent-blog/>
  </div>
</template>

<script>
import SectionRecentBlog from '~/components/Footer.vue';
export default {
  components: { SectionRecentBlog },};
</script>

<style scoped></style>
