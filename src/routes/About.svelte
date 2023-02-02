<script>
  import Navbar from './Navbar.svelte';
  import AboutSocial from './AboutSocial.svelte';
  import AboutDetail from './AboutDetail.svelte';
  import AboutProfile from './AboutProfile.svelte';
  import AboutScroll from './AboutScroll.svelte';
  import leftCorner from '$lib/images/left_corner.svg';
  import rightCorner from '$lib/images/right_corner.svg';
</script>

<section class="about">
  <Navbar />
  <div class="about_outer">
    <div class="about_inner">
      <AboutSocial />
      <AboutDetail />
      <AboutProfile />
    </div>
  </div>
  <AboutScroll />
  <div class="about_svg_left">
    <img src={leftCorner} alt="left_corner" class="about_svg" />
  </div>
  <div class="about_svg_right">
    <img src={rightCorner} alt="right_corner" class="about_svg" />
  </div>
</section>

<style>
  .about {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    position: relative;
    min-height: auto;
  }
  @media only screen and (min-width: 768px) {
    .about {
      min-height: 100vh;
    }
  }
  .about_outer {
    flex: auto;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: var(--gap-l);
    position: relative;
    height: auto;
  }

  .about_inner {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: var(--gap-l);
    position: relative;
    flex-direction: row;
    flex-wrap: wrap-reverse;
  }

  .about_svg {
    display: block;
  }
  .about_svg_left {
    position: absolute;
    left: 0;
    top: 0;
    display: none;
  }
  .about_svg_right {
    position: absolute;
    right: 0;
    bottom: -10px;
    display: none;
  }
</style>
