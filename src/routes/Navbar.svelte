<script>
  import logo from '$lib/images/dk-logo.svg';
  import menu from '$lib/images/menu.svg';
</script>

<div class="card1_navbar">
  <div class="logo_img_ctr"><img src={logo} alt="DK" class="logo_img" /></div>
  <div class="card1_navbar_item card1_navbar_selected">About</div>
  <span class="card1_navbar_item_seperator"> - </span>
  <div class="card1_navbar_item">Skill</div>
  <span class="card1_navbar_item_seperator"> - </span>
  <div class="card1_navbar_item">Services</div>
  <span class="card1_navbar_item_seperator"> - </span>
  <div class="card1_navbar_item">Contact</div>
  <div class="card1_navbar_humburger">
    <img src={menu} alt="menu" class="card1_navbar_humburger_icon" />
  </div>
</div>

<style>
  .logo_img_ctr {
    flex: auto;
  }
  .logo_img {
    display: block;
    height: 50px;
    aspect-ratio: 1/1;
  }

  .card1_navbar {
    display: flex;
    justify-content: flex-end;
    align-items: center;
    gap: 16px;
    padding: 0 24px;
    font-size: 40px;
    font-weight: 100;
    height: 100px;
    background: #000;
    color: #fff;
  }
  .card1_navbar_humburger {
    display: block;
  }
  @media only screen and (min-width: 769px) {
    .card1_navbar_humburger {
      display: none;
    }
  }
  .card1_navbar_humburger_icon {
    filter: invert(100%);
    width: 30px;
    height: 30px;
  }
  .card1_navbar_item_seperator {
    display: none;
  }
  @media only screen and (min-width: 769px) {
    .card1_navbar_item_seperator {
      display: block;
    }
  }
  .card1_navbar_item {
    position: relative;
    cursor: pointer;
    display: none;
  }
  @media only screen and (min-width: 769px) {
    .card1_navbar_item {
      display: block;
    }
  }
  .card1_navbar_selected {
    font-weight: 700;
  }
  .card1_navbar_selected::after {
    content: '';
    width: 100%;
    height: 2px;
    border-radius: 6px;
    background: #111;
    position: absolute;
    left: 0;
    bottom: 0.2em;
  }
</style>
