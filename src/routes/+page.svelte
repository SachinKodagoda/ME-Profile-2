<script>
  import logo from '$lib/images/dk-logo.svg';
  import facebook from '$lib/images/facebook.svg';
  import github from '$lib/images/github.svg';
  import linkedin from '$lib/images/linkedin.svg';
  import youtube from '$lib/images/youtube.svg';
  import menu from '$lib/images/menu.svg';
  import About from './About.svelte';
  import Experience from './Experience.svelte';
  import Skill from './Skill.svelte';
  import './normalize.css';
  import './styles.css';
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
