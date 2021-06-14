<template>
  <section id="home">
    <div class="container">
      <p class="hi">{{ $t('hi') }}</p>
      <h1 class="glitch">{{ $t('frontend') }}</h1>
      <p class="text">
        {{ $t('specialized') }} <router-link :title="$t('contact')" to="/contact">{{ $t('contact_me') }}</router-link>.
      </p>
      <div class="cta">
        <a class="shadow" :title="$t('download')" href="https://github.com/iam-omer-mahdi/CV/archive/refs/heads/main.zip">
          <div class="btn-text">{{ $t('download') }} <i class="lnr lnr-download"></i></div>
          <div class="btn-overlay"></div>
        </a>
      </div>
      <div class="social">
        <a target="_blank" href="https://www.facebook.com/OmerMahdiDev">Facebook</a>
        <a target="_blank" href="https://twitter.com/Omer__Mahdi">Twitter</a>
        <a target="_blank" href="https://github.com/iam-omer-mahdi">Github</a>
      </div>
      <!-- Shapes -->
      <svg
        class="circle"
        width="150"
        height="110"
        viewBox="0 0 182 182"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M139.3 47.3762C144.872 52.9477 149.291 59.562 152.306 66.8416C155.322 74.1211 156.874 81.9233 156.874 89.8026C156.874 97.6819 155.322 105.484 152.306 112.764C149.291 120.043 144.872 126.657 139.3 132.229C133.729 137.801 127.114 142.22 119.835 145.235C112.555 148.251 104.753 149.803 96.8736 149.803C88.9943 149.803 81.1922 148.251 73.9126 145.235C66.6331 142.22 60.0187 137.801 54.4472 132.229L75.6486 111.028C78.4359 113.815 81.745 116.026 85.3867 117.534C89.0285 119.043 92.9318 119.819 96.8736 119.819C100.815 119.819 104.719 119.043 108.361 117.534C112.002 116.026 115.311 113.815 118.099 111.028C120.886 108.24 123.097 104.931 124.605 101.289C126.114 97.6477 126.89 93.7444 126.89 89.8026C126.89 85.8607 126.114 81.9575 124.605 78.3157C123.097 74.6739 120.886 71.3649 118.099 68.5776L139.3 47.3762Z"
          fill="#111"
        />
        <path
          d="M127.279 49.4975C132.851 55.069 137.27 61.6834 140.286 68.9629C143.301 76.2424 144.853 84.0446 144.853 91.9239C144.853 99.8032 143.301 107.605 140.286 114.885C137.27 122.164 132.851 128.779 127.279 134.35C121.708 139.922 115.093 144.341 107.814 147.357C100.534 150.372 92.7321 151.924 84.8528 151.924C76.9735 151.924 69.1713 150.372 61.8918 147.357C54.6123 144.341 47.9979 139.922 42.4264 134.35L63.6278 113.149C66.4151 115.936 69.7241 118.147 73.3659 119.656C77.0077 121.164 80.911 121.941 84.8528 121.941C88.7947 121.941 92.6979 121.164 96.3397 119.656C99.9815 118.147 103.29 115.936 106.078 113.149C108.865 110.362 111.076 107.053 112.585 103.411C114.093 99.769 114.869 95.8657 114.869 91.9239C114.869 87.982 114.093 84.0788 112.585 80.437C111.076 76.7952 108.865 73.4862 106.078 70.6989L127.279 49.4975Z"
          fill="#ef4444"
        />
      </svg>
      <svg
        class="triangle"
        width="106"
        height="80"
        viewBox="0 0 106 103"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M49.9613 20.7104C51.0145 17.8169 54.805 17.1486 56.7843 19.5074L92.6124 62.2056C94.5916 64.5645 93.2752 68.1813 90.2428 68.716L35.351 78.3949C32.3185 78.9296 29.8444 75.9811 30.8976 73.0876L49.9613 20.7104Z"
          fill="#111"
        />
        <path
          d="M37.3447 16.1819C38.3979 13.2884 42.1884 12.62 44.1677 14.9788L79.9958 57.6771C81.9751 60.0359 80.6586 63.6528 77.6262 64.1875L22.7344 73.8664C19.702 74.4011 17.2279 71.4526 18.281 68.5591L37.3447 16.1819Z"
          fill="#fbbf24"
        />
      </svg>
    </div>
  </section>
</template>

<script>
import gsap from "gsap";
export default {
  name: 'Home',
  mounted() {
    // Animation
    gsap.from(".hi", {
      delay: 0.5,
      duration: 0.5,
      y: -20,
      opacity: 0,
      ease: "elastic",
    });
    gsap.from("h1", {
      duration: 0.5,
      y: 20,
      opacity: 0,
      ease: "power2",
    });
    gsap.from(".text", {
      delay: 0.75,
      duration: 1,
      scale: 0.5,
      opacity: 0,
      ease: "power2",
    });
    gsap.from(".cta", {
      delay: 1,
      duration: 0.5,
      // scale: 0.5,
      x: -50,
      opacity: 0,
      ease: "back",
      stagger: {
        amount: 0.5,
      },
    });
    gsap.from(".social a", {
      delay: 1.2,
      duration: 0.5,
      // scale: 0.5,
      y: -50,
      opacity: 0,
      ease: "back",
      stagger: {
        amount: 0.5,
      },
    });
    gsap.from(".circle", {
      delay: 1,
      duration: 0.5,
      width: 0,
      opacity: 0.5,
      ease: "back",
    });
    gsap.from(".triangle", {
      delay: 1.2,
      duration: 0.5,
      width: 0,
      opacity: 0.5,
      ease: "back",
    });

  }
}
</script>

<style scoped lang="scss">
  section {
    position: relative;
    .container {
      position: relative;
      min-height: 87vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
    }
    h1 {
      font-weight: 800;
      font-size: clamp(2rem,5vw,3rem);
      margin: 0;
    }
    p {
      margin: 0;
    }

    .hi {
      font-size: clamp(1rem,5vw,2rem);
    }

    .text {
      font-size: clamp(0.75rem,5vw,1.25rem);
      max-width: 75%;
      a {
        text-decoration: underline;
      }
    }

    a {
      color: var(--light);
    }

    .cta {
      margin-top: 1.75rem;
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      a {
        position: relative;
        font-size: clamp(0.5rem,5vw,1rem);
        font-weight: bold;
        padding: 0.75em 1.25em;
        overflow: hidden;
        color: var(--light);
        border: 2px solid var(--light);
        border-radius: var(--border-radius);
        transition: all 0.4s ease-in-out;
        .btn-overlay {
          background: var(--light);
          z-index: 1;
          position: absolute;
          left: 0;
          top: 0;
          width: 110%;
          height: 110%;
          transform: translateX(-100%);
          transform-origin: center;
          transition: all .3s ease-in-out;
        }
        .btn-text {
          position: relative;
          z-index: 2;
        }
        &:hover {
          color: var(--dark);
          .btn-overlay {
            transform: translateX(0%);
          }
        }
      }
    }
    .social {
      position: absolute;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      right: 0;
      top: 20%;
      bottom: 20%;
      gap: 5;
      &:lang(ar) {
        right: auto;
        left: 0;
      }
      a {
        text-align: center;
        transform: rotate(90deg);
        &::after {
          position: absolute;
          content: '';
          left: 0;
          bottom: 0;
          width: 100%;
          height: 1px;
          background: var(--light);
          transform-origin: left;
          transform: scale(0);
          transition: all ease-in-out 300ms;
        }
        &:hover,&.active{
          color: var(--light);
          &::after {
            transform-origin: right;
            transform: scale(1);
          }
        }
      }
    }
    .circle {
      position: absolute;
      z-index: -1;
      right: 10%;
      bottom: 10%;
      max-height: 90vh;
      animation: float 30s ease-in-out infinite alternate;
    }
    .triangle {
      position: absolute;
      z-index: -1;
      left: 10%;
      top: 10%;
      max-height: 90vh;
      animation: float 30s ease-in-out infinite alternate;
    }
  }

.glitch:hover {
  text-shadow: 0.05em 0 0 rgba(255, 0, 0, 0.75),
    0 0.05em 0 rgba(0, 255, 0, 0.75), -0.05em 0 0 rgba(0, 0, 255, 0.75);
  animation: glitch 350ms infinite;
}

@keyframes glitch {
  0% {
    text-shadow: 0.05em 0 0 rgba(255, 0, 0, 0.75),
      0 0.05em 0 rgba(0, 255, 0, 0.75), -0.05em 0 0 rgba(0, 0, 255, 0.75);
  }
  50% {
    text-shadow: -0.04em 0 0 rgba(255, 0, 0, 0.75),
      0 -0.04em 0 rgba(0, 255, 0, 0.75), 0.04em 0 0 rgba(0, 0, 255, 0.75);
  }
  75% {
    text-shadow: 0 0.04em 0 rgba(255, 0, 0, 0.75),
      0 0.04em 0 rgba(0, 255, 0, 0.75), 0 -0.04em 0 rgba(0, 0, 255, 0.75);
  }
  100% {
    text-shadow: 0em 0.05em 0 rgba(255, 0, 0, 0.75),
      -0.05em 0.05em 0 rgba(0, 255, 0, 0.75),
      -0.05em -0.05em 0 rgba(0, 0, 255, 0.75);
  }
}

@keyframes float {
  0% {
    transform: translate(0) rotate(0);
  }
  25% {
    transform: translate(-3rem, 3rem) rotate(160deg);
  }
  50% {
    transform: translate(-2rem, 3rem) rotate(360deg);
  }
  75% {
    transform: translate(-1.75rem, -1.75rem) rotate(160deg);
  }
  100% {
    transform: translate(0) rotate(0);
  }
}

  @media screen and (max-width: 768px) {
    .container {
      align-items: center !important;
      text-align: center;
      br {
        display: none;
      }
      .text {
        max-width: 100%;
      }
    }
    .social {
      display: none !important;
    }
    .circle {
      width: 80px;
      right: 0;
    }
    .triangle {
      width: 60px;
    }
  }
</style>