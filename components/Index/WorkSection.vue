<template>
  <div class="work-wrapper">
    <h3 class="title">Work</h3>
    <div class="link-group">
      <a href="#!">RewardMe</a>
      <a href="#!">MeFi</a>
      <a href="#!">Measurable Data Tokens</a>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    initiateAnimation() {
      let tl = gsap.timeline()

      tl.from('.work-wrapper .title', {
        y: '200%',
        opacity: 0,
        duration: 0.5,
        stagger: 0.1,
      }).from('.work-wrapper .link-group a', {
        y: '200%',
        opacity: 0,
        duration: 0.5,
        stagger: 0.1,
      })

      ScrollTrigger.create({
        animation: tl,
        trigger: '.work-wrapper',
      })
    },
  },
  mounted() {
    this.initiateAnimation()
  },
}
</script>

<style lang="postcss" scoped>
.work-wrapper {
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
