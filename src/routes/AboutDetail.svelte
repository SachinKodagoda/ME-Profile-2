<script>
  import download from '$lib/images/download.svg';
</script>

<section class="about_details">
  <div class="title_ctr">
    <div class="title">Duminda Kodagoda</div>
    <div class="sub_title_ctr">
      <div class="sub_title_line" />
      <div class="sub_title">Web Developer</div>
    </div>
  </div>
  <div class="description">
    I'm a creative designer and developer who is passionate about web technologies.
  </div>
  <div class="download_ctr">
    <span>DOWNLOAD MY CV</span>
    <img src={download} alt="download" class="download_icon" />
  </div>
</section>

<style>
  .about_details {
    max-width: 580px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: var(--gap-l);
    text-align: center;
  }
  .title {
    font-weight: 800;
    font-size: var(--font3);
  }
  .sub_title {
    font-weight: 300;
    font-size: var(--font2);
  }
  .sub_title_ctr {
    display: flex;
    align-items: center;
    gap: 16px;
  }
  .sub_title_line {
    flex: auto;
    background: #111;
    height: 4px;
    border-radius: 20px;
  }
  .description {
    font-weight: 200;
    color: #8a8a8a;
    font-size: var(--font2);
    line-height: 1.8;
  }
  .download_ctr {
    background: #111;
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 16px 32px;
    border-radius: 50px;
    font-size: var(--font1);
    gap: 16px;
  }
  .download_icon {
    width: calc(var(--font1) * 1.5);
    height: auto;
  }

  @media only screen and (min-width: 768px) {
    .about_details {
      align-items: flex-start;
      text-align: left;
    }
  }
</style>
