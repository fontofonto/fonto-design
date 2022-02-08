<template>
  <div class="page-wrapper">
    <!-- intro -->
    <div class="intro-wrapper">
      <h1 class="my-name">Waikwan Lam</h1>
      <h2 class="short-introduction">
        <span>An User Experience Designer and Frontend Developer.</span>
        <br /><br />
        <span>Now living in Vancouver.</span>
      </h2>
    </div>
    <!-- resume -->
    <div class="resume-wrapper">
      <LinkWithArrow />
    </div>
    <!-- Work -->
    <IndexWorkSection />

    <!-- Side Projects -->
    <IndexSideProjectSection />

    <div class="footer">
      <a
        class="transform hover:scale-110 transition-transform ease-in-out"
        href="#!"
      >
        <IndexContactMeBadge />
      </a>
    </div>

    <LinesBackground />
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  mounted() {
    let tl = new gsap.timeline()

    let nameTextList = new SplitText('.my-name', {
      type: 'chars,words',
      wordsClass: 'overflow-hidden',
      position: 'absolute',
    })
    let introTextList = new SplitText('.short-introduction', {
      type: 'chars,words',
      wordsClass: 'overflow-hidden',
      position: 'absolute',
    })

    tl.from(nameTextList.chars, {
      y: '100%',
      duration: 0.5,
      ease: 'expo.out',
      stagger: 0.05,
    }).from(
      introTextList.chars,
      {
        y: '100%',
        duration: 0.2,
        ease: 'expo.out',
        stagger: 0.01,
      },
      '+=0.1'
    )
  },
}
</script>

<style lang="postcss" scoped>
.page-wrapper {
}
.intro-wrapper {
  @apply w-10/12 mx-auto mt-10;
  .my-name {
    @apply text-6xl md:text-8xl font-bold;
  }
  .short-introduction {
    @apply text-xl md:text-4xl font-medium mt-10;
    /* line-height: 150%; */
    /* Bug: the after pseudo element doesn't work when the window breaks the line */
    /* span {
      @apply relative;
      &:after {
        @apply block absolute -z-[1] w-[102%] h-4 bottom-0 left-1/2 transform -translate-x-1/2 bg-yellow-500 rounded-sm;
        content: '';
      }
    } */
  }
}
.resume-wrapper {
  @apply w-10/12 mx-auto mt-20 text-4xl font-medium text-right;
}

.footer {
  @apply flex items-center justify-center my-40;
}
</style>
