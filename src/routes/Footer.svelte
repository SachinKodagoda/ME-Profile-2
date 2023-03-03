<script lang="ts">
  import codepen from '$lib/images/icon-codepen.svg';
  import github from '$lib/images/icon-github.svg';
  import linkedin from '$lib/images/icon-linkedin.svg';
  import medium from '$lib/images/icon-medium.svg';
  import youtube from '$lib/images/icon-youtube.svg';
  function handleClick() {
    alert('clicked');
  }
</script>

<section class="footer">
  <div class="footer_left">
    <div class="social">
      <div class="social_copy">MORE ABOUT ME</div>
      <div class="social_icon_outer">
        <div class="social_icon_ctr"><img src={github} alt="" class="social_icon" /></div>
        <div class="social_icon_ctr"><img src={codepen} alt="" class="social_icon" /></div>
        <div class="social_icon_ctr"><img src={medium} alt="" class="social_icon" /></div>
        <div class="social_icon_ctr"><img src={youtube} alt="" class="social_icon" /></div>
        <div class="social_icon_ctr"><img src={linkedin} alt="" class="social_icon" /></div>
      </div>
    </div>
    <div class="contacts">
      <div class="contacts_copy">CONTACTS</div>
      <div class="contacts_desc">
        <div class="contacts_desc_item">
          <div class="desc_item_left">EMAIL:</div>
          <div class="desc_item_right">duminda.g.k@gmail.com</div>
        </div>
        <div class="contacts_desc_item">
          <div class="desc_item_left">PHONE:</div>
          <div class="desc_item_right">+94765742200</div>
        </div>
        <div class="contacts_desc_item">
          <div class="desc_item_left">ADDRESS:</div>
          <div class="desc_item_right">296/B, Motemulla, Yogiyana, Sri Lanka</div>
        </div>
      </div>
    </div>
  </div>
  <div class="connect">
    <div class="connect_copy">LET'S CONNECT</div>
    <div class="connect_desc">I do digital design, brand design, and art direction. Send Me an Email</div>
    <form class="email_ctr">
      <div class="input_group">
        <label for="email">Email:</label>
        <input type="text" class="input_email" name="email" placeholder="Enter Your Email Here" />
      </div>
      <div class="input_group">
        <label for="message">Message:</label>
        <textarea name="message" rows="10" cols="30" placeholder="Enter Your Message Here" class="input_textarea" />
      </div>
      <button on:click={handleClick} type="button" class="email_btn">SUBMIT</button>
    </form>
  </div>
</section>

<style>
  .footer {
    background: #000;
    color: #fff;
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    padding: 10rem;
  }

  .footer_left {
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }

  .social {
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }

  .social_copy {
    font-size: 2.5rem;
    font-weight: 900;
    font-family: 'Teko', sans-serif;
    letter-spacing: 0.025em;
    margin-bottom: 1rem;
  }

  .social_icon_outer {
    font-size: 1.5rem;
    color: #8a8a8a;
    margin-bottom: 2rem;
    display: flex;
    gap: 1rem;
    align-items: center;
  }

  .social_icon_ctr {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100px;
    aspect-ratio: 1/1;
    background: #fff;
    border-radius: 50%;
  }

  .social_icon {
    width: 60%;
    height: auto;
  }

  .contacts {
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }

  .contacts_copy {
    font-size: 2.5rem;
    font-weight: 900;
    font-family: 'Teko', sans-serif;
    letter-spacing: 0.025em;
  }

  .contacts_desc {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    font-size: 1.5rem;
    color: #8a8a8a;
  }

  .contacts_desc_item {
    display: flex;
  }

  .desc_item_left {
    width: 150px;
    font-weight: 600;
  }

  .connect {
    display: flex;
    flex-direction: column;
  }

  .connect_copy {
    font-size: 2.5rem;
    font-weight: 900;
    font-family: 'Teko', sans-serif;
    letter-spacing: 0.025em;
    margin-bottom: 1rem;
  }

  .connect_desc {
    font-size: 1.5rem;
    color: #8a8a8a;
    margin-bottom: 2rem;
  }

  .email_ctr {
    font-size: 1.5rem;
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }

  .input_group {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .input_email {
    appearance: none;
    outline: none;
    border: 2px solid #fff;
    background: transparent;
    padding: 1rem;
    border-radius: 4px;
    color: #fff;
  }

  .input_email:focus {
    border-color: #ffc000;
  }

  .input_textarea {
    appearance: none;
    outline: none;
    border: 2px solid #fff;
    background: transparent;
    padding: 1rem;
    border-radius: 4px;
    color: #fff;
  }

  .input_textarea:focus {
    border-color: #ffc000;
  }

  .email_btn {
    all: unset;
    display: inline-block;
    align-self: flex-start;
    background: #ffc000;
    color: #000;
    cursor: pointer;
    padding: 1rem 2rem;
    font-weight: 900;
    border: 2px solid #ffc000;
    border-radius: 4px;
    font-family: 'Teko', sans-serif;
    letter-spacing: 0.025em;
    font-size: 2rem;
  }
</style>
