<script lang="ts">
  import gsap from 'gsap';
  import ScrollTrigger from 'gsap/ScrollTrigger';
  import { onMount } from 'svelte';
  let fTxt: SVGTextElement;
  let experience = 0;
  onMount(() => {
    gsap.registerPlugin(ScrollTrigger);
    const offset = fTxt?.getBBox().height / 2;
    gsap
      .timeline({
        scrollTrigger: {
          trigger: '.fullstack_engineer_txt',
          markers: true,
          start: `center-=${offset} top`,
          pin: true,
          // end: () => `+=${experience}`,
          scrub: 1
          // pinSpacing: false,
          // pin: '.fullstack_text',
          // pin: true,
          // start: 'center center',
          // end: '+=500', // default will be the "top top"
          // toggleClass: '.show_txt'
        }
      })
      .fromTo('.fullstack_engineer_txt', { opacity: 0 }, { opacity: 1 }, 0);
    // ScrollTrigger.create();
  });

  // const txt = node?.querySelector('.f_text');
</script>

<section class="experience">
  <div class="fullstack_engineer_ctr">
    <svg viewBox="0 0 1200 800" xmlns="http://www.w3.org/2000/svg" class="experience_svg">
      <defs>
        <linearGradient id="rainbow" x1="0" x2="0" y1="0" y2="100%" gradientUnits="userSpaceOnUse">
          <stop stop-color="#FF5B99" offset="0%" />
          <stop stop-color="#FF5447" offset="5%" />
          <stop stop-color="#FF7B21" offset="10%" />
          <stop stop-color="#EAFC37" offset="30%" />
          <stop stop-color="#4FCB6B" offset="40%" />
          <stop stop-color="#51F7FE" offset="50%" />
        </linearGradient>
      </defs>
      <mask id="m">
        <g class="cloud1">
          <rect fill="#fff" width="100%" height="801" y="799" />
          <image xlink:href="https://assets.codepen.io/721952/cloud1Mask.jpg" width="1200" height="800" />
        </g>
      </mask>
      <!-- <text x="50%" y="10%" dominant-baseline="middle" text-anchor="middle" fill="#fff">I'M AN</text> -->
      <text fill="url(#rainbow)">
        <tspan x="50%" y="10%" dominant-baseline="middle" text-anchor="middle"> I'M AN </tspan>
        <tspan x="50%" y="30%" dominant-baseline="middle" text-anchor="middle"> EXPERIENCED </tspan>
      </text>
      <text fill="#fff" x="50%" y="50%" dominant-baseline="middle" text-anchor="middle">FULL STACK ENGINEER</text>
      <g mask="url(#m)">
        <rect fill="#fff" width="100%" height="100%" />
        <text x="50%" y="50%" dominant-baseline="middle" text-anchor="middle" fill="#162a43" class="f_text_back"> FULL STACK ENGINEER</text>
      </g>
    </svg>
    <svg viewBox="0 0 1200 800" xmlns="http://www.w3.org/2000/svg" class="fullstack_engineer_txt">
      <text x="50%" y="50%" dominant-baseline="middle" text-anchor="middle" fill="#8a0303" class="f_text" bind:this={fTxt}>FULL STACK ENGINEER</text>
    </svg>
  </div>
  <div class="experience_ctr" bind:offsetHeight={experience} />
</section>

<style>
  .experience {
    height: max-content;
    width: 100%;
    background: #000;
    font-size: 99px;
    font-weight: 900;
    text-align: center;
    position: relative;
  }

  .fullstack_engineer_ctr {
    position: relative;
  }

  .fullstack_engineer_txt {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 100%;
    opacity: 0;
    z-index: 1;
  }
  .experience_svg {
    width: 100%;
    display: block;
  }

  .experience_ctr {
    background: #fff;
    min-height: 100vh;
  }
</style>
