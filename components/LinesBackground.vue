<template>
  <svg class="bg-lines">
    <line
      class="block md:hidden"
      v-for="index in 5"
      :key="`bgline${index}`"
      :x1="`${(100 / 5) * index}%`"
      y1="0%"
      :x2="`${(100 / 5) * index}%`"
      y2="100%"
      stroke="#DEDBD0"
    />
    <line
      class="hidden md:block"
      v-for="index in 13"
      :key="`bgline${index}`"
      :x1="`${(100 / 13) * index}%`"
      y1="0%"
      :x2="`${(100 / 13) * index}%`"
      y2="100%"
      stroke="#DEDBD0"
    />
  </svg>
</template>

<script>
export default {}
</script>

<style lang="postcss" scoped>
.bg-lines {
  width: 100vw;
  height: 100vh;
  position: fixed;
  top: 0;
  left: 0;
  z-index: -99;
}
</style>
