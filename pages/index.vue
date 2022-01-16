<template>
  <div class="page-wrapper">
    <!-- intro -->
    <div class="intro-wrapper">
      <h1 class="title">FONTO</h1>
      <h2 class="subtitle">
        An <span>User Experience Designer</span> and
        <span>Frontend Developer</span> from Hong Kong. <br /><br />Now living
        in Vancouver.
      </h2>
    </div>
    <!-- resume -->
    <div class="resume-wrapper">
      <a href="#!">Get My Resume</a>
    </div>
    <!-- Work -->
    <div class="work-wrapper">
      <h3 class="title">Work</h3>
      <a href="#!">RewardMe</a>
      <a href="#!">MeFi</a>
      <a href="#!">Measurable Data Tokens</a>
    </div>
    <LinesBackground />
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
}
</script>

<style lang="postcss" scoped>
.page-wrapper {
  @apply px-20;
}
.intro-wrapper {
  @apply mt-10;
  .title {
    @apply text-9xl font-bold;
  }
  .subtitle {
    @apply text-4xl font-medium mt-10;
    line-height: 150%;
    span {
      @apply relative;
      &:after {
        @apply block absolute -z-[1] w-[102%] h-4 bottom-0 left-1/2 transform -translate-x-1/2 bg-yellow-500 rounded-sm;
        content: '';
      }
    }
  }
}
.resume-wrapper {
  @apply mt-20 text-4xl font-bold text-right;
}
.work-wrapper {
  @apply mt-40;
  .title {
    @apply font-light italic text-5xl;
  }
  a {
    @apply block font-medium text-7xl mt-10;
  }
}
</style>
