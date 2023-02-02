<script>
  import scroll from '$lib/images/scroll.svg';
</script>

<div class="scroll_ctr1">
  <img src={scroll} alt="scroll" class="scroll_down_mouse1" />
  <span>Scroll Down</span>
</div>

<style>
  .scroll_ctr1 {
    display: flex;
    align-items: center;
    justify-content: center;
    color: #111;
    font-size: var(--s15);
    font-weight: 200;
    gap: 16px;
    padding: 16px;
  }

  .scroll_down_mouse1 {
    width: 34px;
    height: auto;
  }

  @media only screen and (min-width: 425px) {
    .scroll_ctr1 {
      font-size: var(--s20);
    }
  }
</style>
