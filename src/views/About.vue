<template>
  <section id="about">
    <div class="container">
      <h1>{{ $t('about_me') }}</h1>
      <p>{{ $t('whoami') }}</p>
      <p>{{ $t('interested') }}</p>
      <p>{{ $t('i_like') }}</p>
      <p>{{ $t('passion') }}</p>
      <p><router-link to="/contact" title="contact me">{{ $t('something_special') }}</router-link></p>
    </div>
  </section>
</template>

<script>
export default {
    name: 'About',
    metaInfo: {
      title: 'About Me',
      meta: [
        { name: 'description', content: 'Omer Mahdi About Me' },
      ]
    }
}
</script>

<style scoped lang="scss">
  section {
    .container {
      min-height: 85vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
    }
    h1 {
      text-decoration: underline;
    }
    a {
      color: var(--light);
      text-decoration: underline;
    }
    p {
      font-size: 20px;
      margin: 0;
      line-height: 1.4;
      text-align: right;
    }
  }
</style>