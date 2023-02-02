<script>
  import logo from '$lib/images/dk-logo.svg';
  import './normalize.css';
  import './styles.css';
</script>

<svelte:head>
  <title>Home</title>
  <meta name="description" content="Svelte demo app" />
</svelte:head>

<section class="app">
  <header class="header">
    <div class="logo-ctr">
      <img src={logo} alt="DK" class="logo-img" />
    </div>
    <nav class="nav">
      <span aria-current="page" class="nav-items">About</span>
      <span class="nav-items">Skills</span>
      <span class="nav-items">Services</span>
      <span class="nav-items">Contact</span>
    </nav>
  </header>
</section>

<style>
  .app {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }

  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 16px;
    padding: 0 24px;
    height: 60px;
  }

  .logo-ctr {
    width: 3em;
    height: 3em;
  }

  .logo-img {
    width: 2em;
    height: 2em;
    object-fit: contain;
  }

  .nav {
    display: flex;
    justify-content: flex-end;
    gap: 16px;
    font-size: 40px;
    flex: auto;
  }

  .nav-items {
    position: relative;
    cursor: pointer;
    display: none;
    font-weight: 100;
  }
  .nav-items[aria-current='page'] {
    font-weight: 700;
  }
  .nav-items[aria-current='page']::after {
    content: '';
    width: 100%;
    height: 2px;
    border-radius: 6px;
    background: #111;
    position: absolute;
    left: 0;
    bottom: 0.2em;
  }

  @media only screen and (min-width: 769px) {
    .nav-items {
      display: block;
    }
  }
</style>
