<template>
  <section id="contact">
    <div class="container">
      <h1>{{$t('contact')}} <span>{{ $t('me') }}</span></h1>
      <p>{{ $t('contact_text') }} <br /> <a :title="$t('send_email')" href="mailto:iam.omer.mahdi@gmail.com">{{ $t('send_email') }}</a> </p>
      <div class="info">
        <p><i class="lnr lnr-phone"></i>  +249 992359797</p>
        <p><i class="lnr lnr-map"></i> {{ $t('location') }}</p>
        <p><i class="lnr lnr-envelope"></i>  iam.omer.mahdi@gmail.com</p>
      </div>
      <br />
      <div id="map"></div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Contact',
     metaInfo: {
       title: 'Contact Me',
      meta: [
        { name: 'description', content: 'Omer Mahdi Contact Me' },
      ],
    },
    mounted() {
      document.querySelector('#map').innerHTML = '<iframe width="100%" height="100%" style="border:0" loading="lazy" allowfullscreen src="https://www.google.com/maps/embed/v1/place?key=AIzaSyCMNpRxrI9IQhJVKCYIkf3kMb71_AzaTpk&q=East+Nile+Sudan&zoom=11"></iframe>'
    }
}
</script>
<style scoped lang="scss">
  section {
    text-align: center;
  }
  h1 span {
    text-decoration: underline;
  }
  p {
    font-size: clamp(0.75rem,5vw,1.25rem);
  }
  a {
    text-decoration: underline;
    color: var(--light);
  }

  .info {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 1rem;
    p {
      margin: 0;
    }
  }

  #map {
    background-color: var(--light);
    height: 60vh;
  }

  @media screen and (max-width: 768px) {
    section {
      padding-bottom: 5rem;
    }
  }
</style>