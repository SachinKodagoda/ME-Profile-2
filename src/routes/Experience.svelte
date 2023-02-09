<script lang="ts">
  import butterfly1 from '$lib/images/butterfly1.gif';
  import butterfly2 from '$lib/images/butterfly2.gif';
  import hero from '$lib/images/hero.jpg';
  import inkmask from '$lib/images/inkmask.png';
  import gsap from 'gsap';
  import ScrollTrigger from 'gsap/ScrollTrigger';
  import { onMount } from 'svelte';
  let fTxt: SVGTextElement;
  let experience = 0;
  onMount(() => {
    gsap.registerPlugin(ScrollTrigger);
    const offset = fTxt?.getBBox().height * 0.5;
    gsap.timeline({
      scrollTrigger: {
        trigger: '.fullstack_engineer_txt',
        start: `center-=${offset} top`,
        pin: true,
        scrub: 1
      }
    });
    const tl = gsap.timeline({
      scrollTrigger: {
        trigger: '.mask_ctr',
        markers: true,
        start: 'top 30%',
        scrub: 1,
        toggleClass: 'mask_animate'
      }
    });
    tl.to('.f_text', { fill: 'red', duration: 0.4 });
  });
</script>

<section class="experience">
  <div class="fullstack_engineer_ctr">
    <svg viewBox="0 0 1200 800" xmlns="http://www.w3.org/2000/svg" class="experience_svg" preserveAspectRatio="none">
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
      <text fill="url(#rainbow)">
        <tspan x="50%" y="10%" dominant-baseline="middle" text-anchor="middle"> I'M AN </tspan>
        <tspan x="50%" y="30%" dominant-baseline="middle" text-anchor="middle"> EXPERIENCED </tspan>
      </text>
      <text fill="#fff" x="50%" y="50%" dominant-baseline="middle" text-anchor="middle">FULL STACK ENGINEER</text>
      <g mask="url(#m)">
        <rect fill="#fff" width="100%" height="100%" />
        <text x="50%" y="50%" dominant-baseline="middle" text-anchor="middle" fill="#000" class="f_text_back"> FULL STACK ENGINEER</text>
      </g>
    </svg>
    <svg viewBox="0 0 1200 800" xmlns="http://www.w3.org/2000/svg" class="fullstack_engineer_txt">
      <text x="50%" y="50%" dominant-baseline="middle" text-anchor="middle" fill="transparent" stroke="#162a43" stroke-width="2" class="f_text" bind:this={fTxt}>FULL STACK ENGINEER</text>
    </svg>
  </div>
  <section class="hero_section" bind:offsetHeight={experience}>
    <div class="hero_ctr">
      <img src={hero} alt="hero" class="hero_img" />
      <div id="mask" class="mask_ctr" style={`background-image: url(${hero}); -webkit-mask-image: url(${inkmask}); mask-image: url(${inkmask});`} />
      <div style={`background-image: url(${butterfly1})`} class="butterfly1" />
      <div style={`background-image: url(${butterfly2})`} class="butterfly2" />
    </div>
  </section>
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
    z-index: 2;
  }
  .experience_svg {
    width: 100%;
    display: block;
  }

  .hero_section {
    background: #fff;
    display: flex;
    justify-content: flex-end;
  }

  .hero_ctr {
    position: relative;
  }

  .hero_img {
    width: 100vw;
    height: auto;
    display: block;
  }

  @media only screen and (min-width: 768px) {
    .hero_img {
      width: 50vw;
    }
  }

  .mask_ctr {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    background-size: cover;
    background-repeat: no-repeat;
    -webkit-mask-size: cover;
    mask-size: cover;
    -webkit-mask-position: 0% 50%;
    mask-position: 0% 50%;
    /* -webkit-mask-size: 4900% 100%;
    mask-size: 4900% 100%; */
    z-index: 1;
    transition: -webkit-mask-position;
    -webkit-filter: grayscale(100%);
    filter: grayscale(100%);
  }

  :global(.mask_animate) {
    animation: ink 0.7s steps(45) forwards 0.4s;
  }

  @keyframes ink {
    0% {
      -webkit-mask-position: 0 50%;
      mask-position: 0 50%;
    }
    100% {
      -webkit-mask-position: 100% 50%;
      mask-position: 100% 50%;
    }
  }

  .butterfly1 {
    height: 100%;
    pointer-events: none;
    position: absolute;
    width: 100%;
    background-position: 50% 30%;
    background-repeat: no-repeat;
    opacity: 0.8;
    left: 0;
    top: 0;
  }

  .butterfly2 {
    height: 100%;
    pointer-events: none;
    position: absolute;
    width: 100%;
    background-position: 50% 50%;
    background-repeat: no-repeat;
    opacity: 0.8;
    left: 0;
    bottom: 0;
  }
</style>
