<template>
  <section id="parts">
      <h1 class="text-shadow">{{ $t('free_parts') }}</h1>
      <h3 class="text-shadow">{{ $t('soon') }} <i class="lnr lnr-clock"></i>
      </h3>
  </section>
</template>

<script>
export default {
    name: 'Parts',
     metaInfo: {
      title: 'Parts',
      meta: [
        { name: 'description', content: 'Free Website Parts including Navbar, Login Form, Hero Section, Footer And More ...' },
      ]
    }
}
</script>

<style scoped lang="scss">
    section {
        display: grid;
        place-content: center;
        text-align: center;
        min-height: 85vh;
    }
    h1 {
      font-size: clamp(2rem,5vw,3rem);
      margin: 0;
    }
    h3 {
      font-size: clamp(1.75rem,5vw,2.5rem);
      color: var(--light);
      margin: 0;
      i {
        display: inline-block;
        // transition: all 0.2s ease-in-out;
        animation: pulse 2s ease-in-out infinite;
      }
    }

    @keyframes pulse {
        0% {
            transform: rotate(0);
        }
        35% {
            transform: rotate(15deg);
        }
        75% {
            transform: rotate(-15deg);
        }
        100% {
            transform: rotate(0);
        }
    }
</style>