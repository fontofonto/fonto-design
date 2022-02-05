<template>
  <svg class="bg-lines">
    <line
      v-for="index in numberOfLines"
      :key="`bgline${index}`"
      :x1="`${(width / numberOfLines) * index}`"
      y1="0%"
      :x2="`${(width / numberOfLines) * index}`"
      y2="100%"
      stroke="#DEDBD0"
    />
  </svg>
</template>

<script>
export default {
  data: () => ({
    width: 0,
    numberOfLines: 13,
  }),
  methods: {
    handleWindowResize() {
      this.width = document.body.offsetWidth

      this.setNumberOfLines()
    },
    setNumberOfLines() {
      if (window.innerWidth < 768) {
        this.numberOfLines = 5
      } else {
        this.numberOfLines = 13
      }
    },
  },
  mounted() {
    this.handleWindowResize()
    window.addEventListener('resize', () => this.handleWindowResize())
  },
}
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
