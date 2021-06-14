<template>
  <section id="loader">
      <div>
            <svg width="95" height="95" viewBox="0 0 249 293" fill="none" xmlns="http://www.w3.org/2000/svg">
                <rect x="18.5" y="127.5" width="52" height="163" rx="26" fill="white" stroke="white" stroke-width="5"/>
                <rect x="98.5" y="127.5" width="52" height="140" rx="26" fill="white" stroke="white" stroke-width="5"/>
                <rect x="178.5" y="127.5" width="52" height="163" rx="26" fill="white" stroke="white" stroke-width="5"/>
                <rect x="16" y="93" width="217" height="200"/>
                <mask id="path-5-inside-1" fill="white">
                <path fill-rule="evenodd" clip-rule="evenodd" d="M124.5 0C55.7406 0 0 55.7406 0 124.5C0 193.259 55.7406 249 124.5 249C193.259 249 249 193.259 249 124.5C249 55.7406 193.259 0 124.5 0ZM124 37C75.9512 37 37 75.9512 37 124C37 172.049 75.9512 211 124 211C172.049 211 211 172.049 211 124C211 75.9512 172.049 37 124 37Z"/>
                </mask>
                <path d="M10 124.5C10 61.2634 61.2634 10 124.5 10V-10C50.2177 -10 -10 50.2177 -10 124.5H10ZM124.5 239C61.2634 239 10 187.737 10 124.5H-10C-10 198.782 50.2177 259 124.5 259V239ZM239 124.5C239 187.737 187.737 239 124.5 239V259C198.782 259 259 198.782 259 124.5H239ZM124.5 10C187.737 10 239 61.2634 239 124.5H259C259 50.2177 198.782 -10 124.5 -10V10ZM47 124C47 81.4741 81.4741 47 124 47V27C70.4284 27 27 70.4284 27 124H47ZM124 201C81.4741 201 47 166.526 47 124H27C27 177.572 70.4284 221 124 221V201ZM201 124C201 166.526 166.526 201 124 201V221C177.572 221 221 177.572 221 124H201ZM124 47C166.526 47 201 81.4741 201 124H221C221 70.4284 177.572 27 124 27V47Z" fill="white" mask="url(#path-5-inside-1)"/>
            </svg>
            <div class="spinner-box">
                <div class="pulse-container">  
                    <div class="pulse-bubble pulse-bubble-1"></div>
                    <div class="pulse-bubble pulse-bubble-2"></div>
                    <div class="pulse-bubble pulse-bubble-3"></div>
                </div>
            </div>

      </div>
  </section>
</template>

<script>
export default {
    name: 'Loader'
}
</script>

<style scoped lang="scss">
    section {
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        height: 100%;
        width: 100%;
        position: absolute;
        z-index: 20;
        left: 0;
        right: 0;
        top: 0;
        background: var(--primary);
        color: var(--light);
    }
    .pulse-container {    
        margin-top: 1rem;    
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .pulse-bubble {
        width: 1.75rem;
        height: 1.75rem;
        border-radius: 50%;
        background-color: var(--light);
    }

    .pulse-bubble-1 {
        animation: pulse .4s ease 0s infinite alternate;
    }
    .pulse-bubble-2 {
        animation: pulse .4s ease .2s infinite alternate;
    }
    .pulse-bubble-3 {
        animation: pulse .4s ease .4s infinite alternate;
    }
    @keyframes pulse {
        from {
            opacity: 1;
            transform: scale(1);
        }
        to {
            opacity: 0;
            transform: scale(.75);
        }
    }
</style>