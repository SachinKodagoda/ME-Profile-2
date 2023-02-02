<script>
  import github from '$lib/images/github.svg';
  import linkedin from '$lib/images/linkedin.svg';
  import youtube from '$lib/images/youtube.svg';
</script>

<div class="about_inner_left">
  <div class="social_icon_ctr">
    <div class="social_icon">
      <img src={linkedin} alt="linkedin" class="social_icon_img" />
    </div>
    <div class="social_icon">
      <img src={github} alt="github" class="social_icon_img" />
    </div>
    <div class="social_icon">
      <img src={youtube} alt="youtube" class="social_icon_img" />
    </div>
  </div>
</div>

<style>
  .about_inner_left {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .social_icon_ctr {
    width: 200px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: var(--gap-l);
  }
  .social_icon_img {
    width: var(--social-icon);
    height: auto;
  }
</style>
