<template>
    <nav id="nav">
      <div class="container">
        <router-link :title="$t('om')" to="/" class="logo">
          <svg width="35" height="35" viewBox="0 0 249 293" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect x="18.5" y="127.5" width="52" height="163" rx="26" fill="white" stroke="white" stroke-width="5"/>
            <rect x="98.5" y="127.5" width="52" height="140" rx="26" fill="white" stroke="white" stroke-width="5"/>
            <rect x="178.5" y="127.5" width="52" height="163" rx="26" fill="white" stroke="white" stroke-width="5"/>
            <rect x="16" y="93" width="217" height="200"/>
            <mask id="path-5-inside-1" fill="white">
            <path fill-rule="evenodd" clip-rule="evenodd" d="M124.5 0C55.7406 0 0 55.7406 0 124.5C0 193.259 55.7406 249 124.5 249C193.259 249 249 193.259 249 124.5C249 55.7406 193.259 0 124.5 0ZM124 37C75.9512 37 37 75.9512 37 124C37 172.049 75.9512 211 124 211C172.049 211 211 172.049 211 124C211 75.9512 172.049 37 124 37Z"/>
            </mask>
            <path d="M10 124.5C10 61.2634 61.2634 10 124.5 10V-10C50.2177 -10 -10 50.2177 -10 124.5H10ZM124.5 239C61.2634 239 10 187.737 10 124.5H-10C-10 198.782 50.2177 259 124.5 259V239ZM239 124.5C239 187.737 187.737 239 124.5 239V259C198.782 259 259 198.782 259 124.5H239ZM124.5 10C187.737 10 239 61.2634 239 124.5H259C259 50.2177 198.782 -10 124.5 -10V10ZM47 124C47 81.4741 81.4741 47 124 47V27C70.4284 27 27 70.4284 27 124H47ZM124 201C81.4741 201 47 166.526 47 124H27C27 177.572 70.4284 221 124 221V201ZM201 124C201 166.526 166.526 201 124 201V221C177.572 221 221 177.572 221 124H201ZM124 47C166.526 47 201 81.4741 201 124H221C221 70.4284 177.572 27 124 27V47Z" fill="white" mask="url(#path-5-inside-1)"/>
          </svg>
        </router-link>
        <router-link class="nav-link" exact-active-class="active" :title="$t('Home')" to="/"><i class="lnr lnr-home"></i> <span>{{ $t('Home') }}</span></router-link>
        <router-link class="nav-link" exact-active-class="active" :title="$t('About')" to="/about"><i class="lnr lnr-user"></i> <span>{{ $t('About') }}</span></router-link>
        <router-link class="nav-link" exact-active-class="active" :title="$t('Work')" to="/work"><i class="lnr lnr-briefcase"></i> <span>{{ $t('Work') }}</span></router-link>
        <router-link class="nav-link" exact-active-class="active" :title="$t('parts')" to="/parts"><i class="lnr lnr-store"></i> <span>{{ $t('parts') }}</span></router-link>
        <router-link class="nav-link" exact-active-class="active" :title="$t('Contact')" to="/contact"><i class="lnr lnr-envelope"></i> <span>{{ $t('Contact') }}</span></router-link>
        <select @change="changeLang" v-model="lang">
          <option selected disabled hidden value="lang">{{ $t('language') }}</option>
          <option value="en">English</option>
          <option value="ar">العربية</option>
        </select>
      </div>
    </nav>
</template>

<i18n>
{
  "en": {
    "om": "Omer Mahdi",
    "Home": "Home",
    "About": "About",
    "Work": "Work",
    "Contact": "Contact",
    "language": "Language",
    "parts": "Parts"
  },
  "ar": {
    "om": "عمر مهدي",
    "Home": "الرئيسية",
    "About": "نبذة",
    "Work": "اعمالي",
    "Contact": "تواصل معي",
    "language": "اللغة",
    "parts": "الاجزاء"
  }
}
</i18n>


<script>
export default {
  name: 'Navbar',
  data() {
    return {
      lang: 'lang'
    }
  },
  mounted() {
    if (localStorage.lang) {
      this.lang = localStorage.lang
    }
  },
  methods: {
    changeLang() {
      if (this.lang === 'en') {
        this.$root.$i18n.locale = 'en';
        document.querySelector('html').setAttribute('lang', 'en');
        document.querySelector('html').setAttribute('dir', 'ltr');
      } else if (this.lang === 'ar') {
        this.$root.$i18n.locale = 'ar';
        document.querySelector('html').setAttribute('lang', 'ar');
        document.querySelector('html').setAttribute('dir', 'rtl');
      }
    }
  },
  watch: {
    lang(lang) {
      if (lang === 'ar') {
        localStorage.setItem('lang','ar');
         this.$root.$i18n.locale = 'ar';
        document.querySelector('html').setAttribute('lang', 'ar');
        document.querySelector('html').setAttribute('dir', 'rtl');
      } else {
        localStorage.setItem('lang','en');
        this.$root.$i18n.locale = 'en';
        document.querySelector('html').setAttribute('lang', 'en');
        document.querySelector('html').setAttribute('dir', 'ltr');
      }
    }
  }
}
</script>

<style scoped lang="scss">
  nav {
    padding: 0.4rem 0;
    .container {
      max-width: 90%;
      display: flex;
      gap: 1rem;
      align-items: center;
      .logo {
        margin-right: auto;
        display: flex;
        align-items: center;
        img {
          width: 2rem;
          height: 2.2rem;
        }
        &:lang(ar) {
          margin: 0;
          margin-left: auto;
        }
        svg {
          rect:not(:last-of-type),path,mask {
            fill: var(--light);
            stroke: var(--light);
          }
        }
      }
      a:not(.logo) {
        position: relative;
        padding: 0.75rem;
        color: var(--light);
        border-radius: var(--border-radius);
        &::after {
          content: '';
          position: absolute;
          left: 0%;
          bottom: 0;
          width: 100%;
          height: 3px;
          border-radius: 50rem;
          background: var(--light);
          transform: scale(0);
          transform-origin: left;
          transition: all ease-in-out 300ms;
        }
        &:hover,&.active{
          color: var(--light);
          &::after {
            transform: scale(1);
            transform-origin: right;
          }
        }
      }
    }
    select {
      padding: 0.75rem;
      border: 2px solid var(--light);
      background-color: transparent;
      color: var(--light);
      margin-left: auto;
      &:lang(ar) {
        margin-left: 0;
        margin-right: auto;
      }
      option {
        background-color: var(--dark);
      }
    }
  }

  @media screen and (max-width: 768px) {
    nav {
      z-index: 10;
      position: fixed;
      left: 0;
      right: 0;
      bottom: 0;
      overflow-x: auto;
      background: var(--primary);
      border-top: 1px solid #fff;
      .logo {
        display: none !important;
      }
      a:not(.logo) {
        &::after {
          display: none;
        }
        i + span {
          display: none;
        }
      }
      select {
        margin-left: auto;
        &:lang(ar) {
          margin-left: 0;
          margin-right: auto;
        }
      }
    }
  }
</style>