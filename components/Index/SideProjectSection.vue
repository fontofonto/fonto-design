<template>
  <div class="side-project-wrapper">
    <h3 class="title">Side Projects</h3>
    <div class="link-group">
      <a href="#!">Animations</a>
      <a href="#!">Videos</a>
      <a href="#!">Sketches</a>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    initiateAnimation() {
      let tl = gsap.timeline()

      tl.from('.side-project-wrapper .title', {
        y: '200%',
        opacity: 0,
        duration: 0.5,
        stagger: 0.1,
      }).from('.side-project-wrapper .link-group a', {
        y: '200%',
        opacity: 0,
        duration: 0.5,
        stagger: 0.1,
      })

      ScrollTrigger.create({
        animation: tl,
        trigger: '.side-project-wrapper',
      })
    },
  },
  mounted() {
    this.initiateAnimation()
  },
}
</script>

<style lang="postcss" scoped>
.side-project-wrapper {
  @apply w-10/12 mx-auto mt-40;
  .title {
    @apply font-light italic text-5xl;
  }
  .link-group {
    @apply flex flex-col;
  }
  a {
    @apply font-normal text-7xl mt-10;
  }
}
</style>
