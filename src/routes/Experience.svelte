<script lang="ts">
  import butterfly1 from '$lib/images/butterfly1.gif';
  import butterfly2 from '$lib/images/butterfly2.gif';
  import hero from '$lib/images/hero.jpg';
  import inkmask from '$lib/images/inkmask.png';
  import gsap from 'gsap-trial';
  import DrawSVGPlugin from 'gsap-trial/DrawSVGPlugin';
  import MotionPathPlugin from 'gsap-trial/MotionPathPlugin';
  import ScrollTrigger from 'gsap-trial/ScrollTrigger';

  import { onMount } from 'svelte';
  let fTxt: SVGTextElement;
  let experience = 0;
  onMount(() => {
    gsap.registerPlugin(ScrollTrigger, DrawSVGPlugin, MotionPathPlugin);

    const offset = fTxt?.getBBox().height * 0.5;

    gsap.timeline({
      scrollTrigger: {
        trigger: '.fullstack_engineer_txt',
        start: `center-=${offset} top`,
        pin: true,

        end: 'bottom 25%',
        scrub: 1.5
      }
    });

    const tl = gsap.timeline({
      scrollTrigger: {
        trigger: '.mask_ctr',
        start: 'top 10%',
        scrub: 1.5,
        toggleClass: 'mask_animate'
      }
    });
    tl.to('.f_text', { fill: 'red', duration: 0.4 });

    const pulses = gsap
      .timeline({
        defaults: {
          duration: 0.05,
          autoAlpha: 1,
          scale: 2,
          transformOrigin: 'center',
          ease: 'elastic(2.5, 1)'
        }
      })
      .to('.ball01, .text01, .text01_1, .text01_2', {}, 0.2)
      .to('.ball02, .text02, .text02_1, .text02_2', {}, 0.3)
      .to('.ball03, .text03, .text03_1, .text03_2', {}, 0.4)
      .to('.ball04, .text04, .text04_1, .text04_2', {}, 0.5)
      .to('.ball05, .text05, .text05_1, .text05_2', {}, 0.8);

    gsap
      .timeline({
        defaults: { duration: 1 },
        scrollTrigger: {
          trigger: '#time_line_id',
          scrub: true,
          markers: true,
          start: 'top center',
          end: 'bottom 80%'
        }
      })
      .to('.ball00', { duration: 0.01, autoAlpha: 1 })
      .from('.theLine', { drawSVG: 0 }, 0)
      .to(
        '.ball00',
        {
          motionPath: {
            path: '.theLine',
            align: '.theLine',
            alignOrigin: [0.5, 0.5]
          }
        },
        0
      )
      .add(pulses, 0);
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
        <text x="50%" y="50%" dominant-baseline="middle" text-anchor="middle" fill="#000" class="f_text_back">FULL STACK ENGINEER</text>
      </g>
    </svg>
    <svg viewBox="0 0 1200 800" xmlns="http://www.w3.org/2000/svg" class="fullstack_engineer_txt">
      <text x="50%" y="50%" dominant-baseline="middle" text-anchor="middle" fill="transparent" stroke="#162a43" stroke-width="2" class="f_text" bind:this={fTxt}>FULL STACK ENGINEER</text>
    </svg>
  </div>
  <section class="hero_section" bind:offsetHeight={experience}>
    <div class="time_line">
      <svg id="time_line_id" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 600" class="time_line_svg" preserveAspectRatio="none">
        <path class="line01 line" d="M 0 100 600 100" stroke-dasharray="10 10" />
        <path class="line02 line" d="M 0 200 600 200" stroke-dasharray="10 10" />
        <path class="line03 line" d="M 0 300 600 300" stroke-dasharray="10 10" />
        <path class="line04 line" d="M 0 400 600 400" stroke-dasharray="10 10" />
        <path class="line05 line" d="M 0 500 600 500" stroke-dasharray="10 10" />
        <text class="first txt text01" x="90" y="80" text-anchor="middle" dominant-baseline="middle" />
        <text class="second txt text01_1" x="450" y="80" text-anchor="middle" dominant-baseline="middle">BSc (Hons) in IT</text>
        <text class="last txt text01_2" x="450" y="120" text-anchor="middle" dominant-baseline="middle">@SLIIT</text>

        <text class="first txt text02" x="90" y="180" text-anchor="middle" dominant-baseline="middle">2015 - 2017</text>
        <text class="second txt text02_1" x="450" y="180" text-anchor="middle" dominant-baseline="middle">Senior SE</text>
        <text class="last txt text02_2" x="450" y="220" text-anchor="middle" dominant-baseline="middle">@Arit Co., Ltd</text>

        <text class="first txt text03" x="90" y="280" text-anchor="middle" dominant-baseline="middle">2017 - 2020</text>
        <text class="second txt text03_1" x="450" y="280" text-anchor="middle" dominant-baseline="middle">Senior SE</text>
        <text class="last txt text03_2" x="450" y="320" text-anchor="middle" dominant-baseline="middle">@Takumi Tech (pvt) Ltd</text>

        <text class="first txt text04" x="90" y="380" text-anchor="middle" dominant-baseline="middle">2020 - 2021</text>
        <text class="second txt text04_1" x="450" y="380" text-anchor="middle" dominant-baseline="middle">Freelancer</text>
        <text class="last txt text04_2" x="450" y="420" text-anchor="middle" dominant-baseline="middle">@WDA</text>

        <text class="first txt text05" x="90" y="480" text-anchor="middle" dominant-baseline="middle">from 2021</text>
        <text class="second txt text05_1" x="450" y="480" text-anchor="middle" dominant-baseline="middle">FullStack Engineer</text>
        <text class="last txt text05_2" x="450" y="520" text-anchor="middle" dominant-baseline="middle">@Noon Lanka (pvt) Ltd</text>

        <path
          class="theLine"
          d="M 210.369 0 C 233.709 62.871 262.885 -3.26 260 109.552 V 200 V 300 V 400 V 500 C 260.94 578.307 280.39 591.922 315.401 558.856"
          fill="none"
          stroke="#800000"
          stroke-width="5px"
          stroke-linecap="round"
        />

        <circle class="ball ball00" r="5" cx="50" cy="100" />
        <circle class="ball ball01" r="6" cx="260" cy="100" />
        <circle class="ball ball02" r="6" cx="260" cy="200" />
        <circle class="ball ball03" r="6" cx="260" cy="300" />
        <circle class="ball ball04" r="6" cx="260" cy="400" />
        <circle class="ball ball05" r="6" cx="260" cy="500" />
      </svg>
    </div>
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
    justify-content: center;
    align-items: center;
    gap: 16px;
  }

  .time_line {
    flex: none;
    width: calc(50vw - 40px);
  }

  .hero_ctr {
    position: relative;
    flex: none;
    width: calc(50vw - 40px);
  }

  .hero_img {
    width: 100%;
    height: auto;
    display: block;
  }

  /* @media only screen and (min-width: 768px) {
    .hero_img {
      width: 50vw;
    }
  } */

  .mask_ctr {
    position: absolute;
    inset: 0;
    width: 100%;
    aspect-ratio: 1 / 1;
    /* height: auto; */
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
  .time_line_svg {
    height: 100%;
    width: auto;
    overflow: visible;
    padding: 16px;
  }

  .ball {
    fill: #bf0000;
    visibility: hidden;
  }

  .ball00 {
    fill: #000;
  }

  .line {
    fill: none;
    stroke: #800000;
    stroke-width: 1px;
    stroke-linecap: round;
    opacity: 0.5;
  }

  .txt {
    visibility: hidden;
  }

  .first {
    fill: #400000;
    font-weight: 100;
    font-size: 14px;
  }

  .second {
    fill: rgba(0, 0, 0, 1);
    font-weight: 400;
    font-size: 14px;
  }

  .last {
    fill: rgba(0, 0, 0, 0.4);
    font-weight: 200;
    font-size: 13px;
  }
</style>
