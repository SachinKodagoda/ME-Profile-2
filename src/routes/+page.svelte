<script>
  import gsap from 'gsap';
  import ScrollTrigger from 'gsap/ScrollTrigger';
  import { onMount } from 'svelte';
  import About from './About.svelte';
  import Experience from './Experience.svelte';
  import './normalize.css';
  import Skill from './Skill.svelte';
  import './styles.css';

  onMount(() => {
    gsap.registerPlugin(ScrollTrigger);
    const w = document.querySelector('.background_font_inner');
    const [xFrom, xTo] = ['100%', '-100%'];
    gsap.fromTo(
      w,
      { x: xFrom },
      {
        x: xTo,
        scrollTrigger: {
          trigger: '.background_font_inner',
          scrub: 0.1
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

<section id="smooth-wrapper" class="app">
  <div id="smooth-content">
    <About />
    <Skill />
    <Experience />
  </div>
</section>

<style>
  #smooth-content {
    overflow: visible;
    height: 400vh;
    display: flex;
    width: 100%;
    flex-direction: column;
  }
</style>
