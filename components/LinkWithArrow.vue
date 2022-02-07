<template>
  <a
    ref="link-with-arrow"
    href="#!"
    class="link-with-arrow"
    @mouseover="isHover = true"
    @mouseleave="isHover = false"
  >
    <span>Check Out My Resume</span>
    <Arrow :isActive="isHover" />
  </a>
</template>

<script>
export default {
  data: () => ({
    isHover: false,
  }),
}
</script>

<style lang="postcss" scoped>
.link-with-arrow {
  @apply inline-flex flex-row items-center space-x-4;
}
</style>
