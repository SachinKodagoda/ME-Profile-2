<script>
  import gsap from 'gsap-trial';
  import ScrollSmoother from 'gsap-trial/ScrollSmoother';
  import ScrollTrigger from 'gsap-trial/ScrollTrigger';
  import { onMount } from 'svelte';
  import About from './About.svelte';
  import Experience from './Experience.svelte';
  import Footer from './Footer.svelte';
  import './normalize.css';
  import Skill from './Skill.svelte';
  import './styles.css';
  let progressVal = 0;
  onMount(() => {
    gsap.registerPlugin(ScrollTrigger, ScrollSmoother);
    ScrollSmoother.create({
      smooth: 1,
      effects: true,
      smoothTouch: 0.1
    });
    const w = document.querySelector('.background_font_inner');
    const [xFrom, xTo] = ['100%', '-100%'];
    gsap.fromTo(
      w,
      { x: xFrom },
      {
        x: xTo,
        scrollTrigger: {
          trigger: '.background_font_inner',
          scrub: 0.1,
          onUpdate: (self) => {
            progressVal = self.progress * 1.5;
          }
        }
      }
    );

    gsap
      .timeline({
        scrollTrigger: {
          trigger: '.experience',
          start: 'top center',
          // markers: true,
          scrub: 1
        }
      })
      .fromTo('.cloud1', { y: 0 }, { y: -800 }, 0);
  });
</script>

<svelte:head>
  <title>Home</title>
  <meta name="description" content="Svelte demo app" />
</svelte:head>

<section id="smooth-wrapper" class="app" style="--progress: {progressVal}">
  <div id="smooth-content">
    <About />
    <Skill />
    <Experience />
    <Footer />
  </div>
</section>

<style>
  #smooth-content {
    overflow: visible;
    height: 500vh;
    display: flex;
    width: 100%;
    flex-direction: column;
  }
</style>
