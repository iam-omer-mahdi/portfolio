<template>
  <section id="work">
    <div class="container">
      <h1>{{ $t('work') }}</h1>
      <div class="projects">
        <article>
          <img src="@/assets/images/work/world_countries.png" alt="World Countries">
          <div class="overlay">
            <a target="_blank" title="world Countries" href="https://om-world.netlify.app">
              <div class="btn-text">{{ $t('view_project' )}}</div>
              <div class="btn-overlay"></div>
            </a>
          </div>
        </article>
        <article>
          <img src="@/assets/images/work/Company.png" alt="Company Project">
          <div class="overlay">
            <a target="_blank" title="company" href="https://om-company.netlify.app">
              <div class="btn-text">{{ $t('view_project' )}}</div>
              <div class="btn-overlay"></div>
            </a>
          </div>
        </article>
        <article>
          <img src="@/assets/images/work/Assassin-s-Creed.png" alt="Assassin creed">
          <div class="overlay">
            <a target="_blank" title="assassins creed" href="https://iam-omer-mahdi.github.io/AssAssin-Creed/">
              <div class="btn-text">{{ $t('view_project' )}}</div>
              <div class="btn-overlay"></div>
            </a>
          </div> 
        </article>
      </div>
    </div>
  </section>
</template>

<script>
export default {
    name: 'Work',
     metaInfo: {
      title: 'My Work',
      meta: [
        { name: 'description', content: 'Omer Mahdi My Work' },
      ]
    }
}
</script>

<style scoped lang="scss">
  section {
    overflow: hidden;
    padding-bottom: 3rem;
    .container {
      text-align: center;
      h1 {
        text-decoration: underline;
      }
      .projects {
        perspective: 1000px;
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        justify-content: center;
        gap: 1rem;
      }
      article {
        box-shadow: 2px 2px 5px rgba(#000, 0.3);
        position: relative;
        width: 50%;
        height: 50vh;
        img {
          width: 100%;
          height: 100%;
        }
        transition: all 0.3s ease-in-out;
        transform: rotateX(15deg);
        &:hover 
        {
          transform: rotateX(0deg);
          .overlay {
            opacity: 1;
          }
        }
      }

      .overlay {
        position: absolute;
        width: 100.1%;
        height: 100.1%;
        top: 0;
        left: 0;
        background-color: rgba(#000, 0.9);
        opacity: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        transition: all 0.3s ease-in-out;
        a {
          position: relative;
          overflow: hidden;
          font-weight: bold;
          color: #fff;
          padding: .5rem;
          border: 1px solid #fff;
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
            color: var(--primary);
            .btn-overlay {
              transform: translateX(0%);
            }
          }
        }
      }

    }
  }

  @media screen and (max-width: 768px) {
    article {
      width: 100% !important;
      height: 30vh !important;
    }
  }
</style>