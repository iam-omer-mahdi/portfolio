<template>
  <div id="app">
    <Loader v-if="loading"></Loader>
    <div class="theme">
      <button title="dark theme" class="dark" @click="theme = 'dark'"><i class="lnr lnr-moon"></i></button>
      <button title="light theme" class="light" @click="theme = 'light'"><i class="lnr lnr-sun"></i></button>
    </div>
    <Navbar></Navbar>
    <main>
      <router-view/>
    </main>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue"
import Loader from '@/components/Loader.vue';
export default {
  metaInfo: {
    // if no subcomponents specify a metaInfo.title, this title will be used
    title: 'Front-End Web Developer',
    // all titles will be injected into this template
    titleTemplate: 'Omer Mahdi - %s',
    meta: [
      { name: 'description', content: 'Omer Mahdi Portfolio Front End Web Developer Specialized In Custom Theme Development' },
      { name: 'keywords', content: 'Omer Mahdi,Portfolio,Front End,Web Developer,Custom Theme,Development,om,omer mahdi,frontend developer,عمر مهدي,مصمم مواقع' },
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      { property: "og:title", content: "Omer Mahdi - Frontend Web Developer"},
      { property: "og:type", content: "website"},
      { property: "og:url", content: "https://www.omer-mahdi.com/"},
      { property: "og:image", content: "/social.png"},
      { property: "og:locale", content: "en_GB"},
      { property: "og:locale:alternate", content:"ar_SA"},
      { property:"twitter:card", content:"summary_large_image" },
      { property:"twitter:image", content:"/social.png" },
      { property:"twitter:site", content:"@Omer__Mahdi" }
    ]
  },
  data() {
    return {
      loading: true,
      theme: 'dark',
    }
  },
  watch: {
    theme(theme) {
      if (theme == 'light') {
        document.documentElement.style.setProperty('--primary','#0984e3');
        document.querySelector('.dark').style.display = "block";
        document.querySelector('.light').style.display = "none";
        localStorage.setItem('theme','light');
      } else if (theme == 'dark') {
        document.documentElement.style.setProperty('--primary','#1f2937');
        document.querySelector('.dark').style.display = "none";
        document.querySelector('.light').style.display = "block";
        localStorage.setItem('theme','dark');
      }
    }
  },
  mounted() {
    this.loading = false;
    if (localStorage.theme) {
      this.theme = localStorage.theme
    }
  },
  components: {
    Navbar,
    Loader
  },
}
</script>

<style lang="scss">
:root {
  --primary: #1f2937;
  --yellow: #fdcb6e;
  --blue: #0984e3;
  --red: #d63031;
  --green: #00b894;
  --indigo: #6c5ce7;
  --light: #fff;
  --dark: #1f2937;
  --border-radius: 0;
}

html {
  scroll-behavior: smooth;
  scrollbar-color: var(--light) var(--primary);
}

::selection {
  background-color: rgba(#000, 0.7);
}

::-webkit-scrollbar {
  width: 0.5rem;
  background-color: var(--primary);
  color: var(--primary);
  box-shadow: inset 2px 2px 3px rgba(#000, 0.6);
}

::-webkit-scrollbar-thumb {
  background: var(--light);
}

body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  line-height: 1.4;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-family: 'Nunito', Helvetica, Arial, sans-serif;
  &:lang(ar) {
    font-family: 'Tajawal','Nunito', Helvetica, Arial, sans-serif;
  }
  color: var(--light);
  background: var(--primary);
}

a {
  text-decoration: none;
}

h1,h2,h3,h4,p,.social a,.text-shadow {
  text-shadow: 2px 2px 3px rgba(#000, 0.3);
}

.shadow {
  box-shadow: 2px 2px 3px rgba(#000, 0.3);
}

* {
  &:focus {
    outline: 1px dashed var(--light);
    outline-offset: 4px;
  }
}

#app {
  min-height: 100vh;
}

.container {
  max-width: 90%;
  margin: 0 auto;
}

main {
  padding: 1rem 0;
}

.theme {
  position: fixed;
  z-index: 10;
  right: 0;
  top: 25vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  .dark {
    display: none;
  }
  .dark,
  .light {
    background-color: var(--light);
    color: var(--dark);
  }
}

button {
  padding: .5rem .6rem;
  border: none;
  border-radius: var(--border-radius);
  color: var(--dark);
  cursor: pointer;
  margin: 0 .3rem;
  i {
    font-size: 1rem;
  }
}

@media screen and (max-width: 768px) {
  .theme {
    top: 10vh;
  }
}
</style>
