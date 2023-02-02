<script>
  import download from '$lib/images/download.svg';
</script>

<section class="about_inner_middle">
  <div class="about_title_ctr">
    <div class="about_title">Duminda Kodagoda</div>
    <div class="about_sub_title_ctr">
      <div class="about_sub_title_line" />
      <div class="about_sub_title">Web Developer</div>
    </div>
  </div>
  <div class="about_description">
    I'm a creative designer and developer who is passionate about web technologies.
  </div>
  <div class="about_download_ctr">
    <span>DOWNLOAD MY CV</span>
    <img src={download} alt="download" />
  </div>
</section>

<style>
  .about_inner_middle {
    max-width: 580px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }
  .about_title {
    font-weight: 800;
    font-size: 32px;
  }
  .about_sub_title {
    font-weight: 300;
    font-size: 16px;
  }
  .about_sub_title_ctr {
    display: flex;
    align-items: center;
    gap: 16px;
  }
  .about_sub_title_line {
    flex: auto;
    background: #111;
    height: 4px;
    border-radius: 20px;
  }

  .about_description {
    font-weight: 200;
    color: #8a8a8a;
    font-size: 32px;
    line-height: 1.8;
  }

  .about_download_ctr {
    background: #111;
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 16px 32px;
    border-radius: 50px;
    font-size: 32px;
    margin-top: 52px;
    gap: 16px;
  }
</style>
