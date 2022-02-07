<template>
  <svg
    class="link-with-arrow"
    width="100"
    height="30"
    viewBox="0 0 100 30"
    fill="none"
  >
    <line
      class="tail"
      x1="0"
      y1="50%"
      x2="95%"
      y2="50%"
      stroke="black"
      stroke-width="4"
    />
    <path
      class="head"
      fill-rule="evenodd"
      clip-rule="evenodd"
      d="M85.4142 0.585785L99.8285 15L85.4142 29.4142L82.5858 26.5858L94.1716 15L82.5858 3.41421L85.4142 0.585785Z"
      fill="black"
    />
  </svg>
</template>

<script>
export default {
  props: ['isActive'],
  data: () => ({
    length: 80,
    tweenedLength: 80,
    headpath:
      'M65.4142 0.585785L79.8285 15L65.4142 29.4142L62.5858 26.5858L74.1716 15L62.5858 3.41421L65.4142 0.585785Z',
    tailpath: 'M0 15H77.6',
  }),
  watch: {
    isActive: function (newValue) {
      if (newValue) {
        this.length = 103
      } else {
        this.length = 80
      }
    },
    length: function (newValue) {
      gsap.to(this.$data, { duration: 0.5, tweenedLength: newValue })
    },
  },
}
</script>

<style lang="postcss" scoped>
.link-with-arrow,
.head,
.tail {
  transition: all 1s ease;
}
.head {
  position: absolute;
  top: 50%;
  right: 0;
}
</style>
