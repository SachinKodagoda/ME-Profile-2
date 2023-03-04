<script lang="ts">
  import back from '$lib/images/back6.jpeg';
  import logo from '$lib/images/dk-logo.svg';
  import download from '$lib/images/download.svg';
  import fire from '$lib/images/fire.gif';
  import codepen from '$lib/images/icon-codepen.svg';
  import github from '$lib/images/icon-github.svg';
  import linkedin from '$lib/images/icon-linkedin.svg';
  import medium from '$lib/images/icon-medium.svg';
  import youtube from '$lib/images/icon-youtube.svg';
  // import inkmask from '$lib/images/inkmask.png';
  import leftCorner from '$lib/images/left_corner.svg';
  import hero from '$lib/images/main.jpg';
  import menu from '$lib/images/menu.svg';
  import profile from '$lib/images/profile1.jpg';
  import scroll from '$lib/images/scroll.svg';
  import gsap from 'gsap-trial';
  import DrawSVGPlugin from 'gsap-trial/DrawSVGPlugin';
  import MotionPathPlugin from 'gsap-trial/MotionPathPlugin';
  import ScrollSmoother from 'gsap-trial/ScrollSmoother';
  import ScrollTrigger from 'gsap-trial/ScrollTrigger';
  import { onMount } from 'svelte';
  import './normalize.css';
  import './styles.css';

  function handleClick() {
    alert('clicked');
  }
  let skillValue = 0;
  let fTxt: SVGTextElement;
  let experience = 0;
  let curveValue = 0;
  const maxCurveVh = 20;
  onMount(() => {
    gsap.registerPlugin(ScrollTrigger, ScrollSmoother, DrawSVGPlugin, MotionPathPlugin);
    ScrollSmoother.create({
      smooth: 1,
      effects: true,
      smoothTouch: 0.1
    });

    const mm = gsap.matchMedia();

    //  🔥🔥🔥 SkillSection 🔥🔥🔥
    const w = document.querySelector('.skill_background_font_inner');
    gsap.fromTo(
      w,
      { x: '100%' },
      {
        x: '-100%',
        scrollTrigger: {
          trigger: '.skill_background_font_inner',
          scrub: true,
          onUpdate: (self) => {
            skillValue = self.progress * 1.5;
          }
        }
      }
    );

    //  🔥🔥🔥 ExperienceSection 🔥🔥🔥
    gsap
      .timeline({
        scrollTrigger: {
          trigger: '.experience_section',
          start: 'top center',
          scrub: true
        }
      })
      .fromTo('.experience_cloud1', { y: 0 }, { y: -800 }, 0);
    const pulses = gsap
      .timeline({
        defaults: {
          duration: 0.05,
          autoAlpha: 1,
          scale: 2,
          transformOrigin: 'center',
          ease: 'elastic(2.5, 1)'
        }
      })
      .to('.experience_ball01, .experience_text01, .experience_line01', {}, 0.2)
      .to('.experience_ball02, .experience_text02, .experience_line02', {}, 0.3)
      .to('.experience_ball03, .experience_text03, .experience_line03', {}, 0.4)
      .to('.experience_ball04, .experience_text04, .experience_line04', {}, 0.5)
      .to('.experience_ball05, .experience_text05, .experience_line05', {}, 0.8);

    const lines = gsap
      .timeline({
        defaults: {
          duration: 0.05,
          autoAlpha: 1,
          transformOrigin: 'center left',
          ease: 'elastic(2.5, 1)'
        }
      })
      .to(' .text01_1, .text01_2', {}, 0.2)
      .to(' .text02_1, .text02_2', {}, 0.3)
      .to(' .text03_1, .text03_2', {}, 0.4)
      .to(' .text04_1, .text04_2', {}, 0.5)
      .to(' .text05_1, .text05_2', {}, 0.8);

    gsap
      .timeline({
        defaults: { duration: 1 },
        scrollTrigger: {
          trigger: '#time_line_id',
          scrub: true,
          start: 'top center',
          end: 'bottom 80%'
        }
      })
      .to('.experience_ball00', { duration: 0.01, autoAlpha: 1 })
      .from('.experience_theLine', { drawSVG: 0 }, 0)
      .to(
        '.experience_ball00',
        {
          motionPath: {
            path: '.experience_theLine',
            align: '.experience_theLine',
            alignOrigin: [0.5, 0.5]
          }
        },
        0
      )
      .add(pulses, 0)
      .add(lines, 0);
    //  🔥🔥🔥 FooterSection 🔥🔥🔥
    mm.add('(max-width: 768px)', () => {
      curveValue = 0;
      ScrollTrigger.create({
        trigger: '.footer_rounded_div',
        scrub: true,
        start: 'top 80%',
        end: 'bottom 50%',
        onUpdate: (self) => {
          curveValue = maxCurveVh / 4 - (self.progress * maxCurveVh) / 4;
        }
      });
    });
    mm.add('(min-width: 769px)', () => {
      curveValue = maxCurveVh;
      ScrollTrigger.create({
        trigger: '.footer_rounded_div',
        scrub: true,
        start: 'top bottom',
        end: 'top 40%',
        markers: true,
        onUpdate: (self) => {
          curveValue = maxCurveVh - self.progress * maxCurveVh;
        }
      });
    });
  });
</script>

<svelte:head>
  <title>Home</title>
  <meta name="description" content="Svelte demo app" />
</svelte:head>

<section id="smooth-wrapper" class="app" style="--progress: {skillValue}">
  <div id="smooth-content">
    <!-- 🔥🔥🔥 AboutSection 🔥🔥🔥 -->
    <section class="about_section" style={`background-image: url(${back})`}>
      <!-- 🔥🔥🔥 AboutSection-Navbar 🔥🔥🔥 -->
      <div class="navbar">
        <div class="logo_img_ctr"><img src={logo} alt="DK" class="logo_img" /></div>
        <div class="navbar_item navbar_item_selected">About</div>
        <span class="navbar_item_separator"> - </span>
        <div class="navbar_item">Skill</div>
        <span class="navbar_item_separator"> - </span>
        <div class="navbar_item">Experience</div>
        <span class="navbar_item_separator"> - </span>
        <div class="navbar_item">Contact</div>
        <div class="hamburger">
          <img src={menu} alt="menu" class="hamburger_icon" />
        </div>
      </div>
      <!-- 🔥🔥🔥 AboutSection-AboutMiddle 🔥🔥🔥 -->
      <div class="about">
        <div class="about_inner">
          <!-- 🔥🔥🔥 AboutSection-AboutMiddle-Left 🔥🔥🔥 -->
          <div class="about_left">
            <div class="about_social_icon_ctr">
              <div class="about_social_icon">
                <img src={linkedin} alt="linkedin" class="about_social_icon_img" />
              </div>
              <div class="about_social_icon">
                <img src={github} alt="github" class="about_social_icon_img" />
              </div>
              <div class="about_social_icon">
                <img src={youtube} alt="youtube" class="about_social_icon_img" />
              </div>
            </div>
          </div>
          <!-- 🔥🔥🔥 AboutSection-AboutMiddle-Middle 🔥🔥🔥 -->
          <section class="about_middle">
            <div class="about_title_ctr">
              <!-- <div class="about_title" style={`background-image: url(${name_back})`}>Duminda Kodagoda</div> -->
              <div class="about_title2">Duminda Kodagoda</div>
              <div class="about_sub_title_ctr">
                <div class="about_sub_title_line" />
                <div class="about_sub_title">Web Developer</div>
              </div>
            </div>
            <div class="about_description">I'm a creative designer and developer who is passionate about web technologies.</div>
            <div class="about_download_ctr">
              <span>DOWNLOAD MY CV</span>
              <img src={download} alt="download" class="about_download_icon" />
            </div>
          </section>
          <!-- 🔥🔥🔥 AboutSection-AboutMiddle-Right 🔥🔥🔥 -->
          <div class="about_right">
            <div class="about_profile_ctr" id="about_profile_ctr" style={`background-image: url(${profile})`} />
          </div>
        </div>
      </div>

      <!-- 🔥🔥🔥 AboutSection-Scroll 🔥🔥🔥 -->
      <div class="scroll_ctr">
        <img src={scroll} alt="scroll" class="scroll_down_mouse" />
        <span>Scroll Down</span>
      </div>
      <!-- 🔥🔥🔥 AboutSection-Corners 🔥🔥🔥 -->
      <div class="about_svg_left">
        <img src={leftCorner} alt="left_corner" class="about_svg" />
      </div>
      <div class="about_svg_right">
        <img src={leftCorner} alt="right_corner" class="about_svg" />
      </div>
    </section>
    <!-- 🔥🔥🔥 SkillSection 🔥🔥🔥 -->
    <div class="skill_section">
      <div class="skill_inner">
        <div class="skill_background_font">
          <span class="skill_background_font_inner" data-word="FULLSTACK">FULLSTACK</span>
        </div>
        <div class="skill_right">
          <div class="skill_right_inner">
            <div>
              <span data-word="Html,">Html,</span>
              <span data-word="CSS,">CSS,</span>
              <span data-word="JS">JS</span>
            </div>
            <div>
              <span data-word="React,">React,</span>
              <span class="skill_word skill_word_special" data-word="Next.js">
                Next.js
                <svg width="50" height="5" viewBox="0 0 50 5" fill="none" xmlns="http://www.w3.org/2000/svg" class="skill_wave">
                  <path
                    d="M1 2C2.5 1.55556 5.2 1 8 1C11.5 1 13.5 3 16 3C18.5 3 21 1 23.5 1C26 1 26.5 3 33 3C39.5 3 37.5 2 41.5 1.33333C45 0.75 47.6667 1.55556 49.5 2"
                    stroke="#8a0303"
                    stroke-linecap="round"
                    class="skill_wave_path"
                  />
                </svg>
              </span>
            </div>
            <div>
              <span data-word="MySQL,">MySQL,</span>
              <span data-word="Firebase,">Firebase</span>
            </div>
            <div>
              <span data-word="Node,">Node,</span>
              <span data-word="Python,">Python,</span>
              <span data-word="PHP">PHP</span>
            </div>
            <div>
              <span data-word="Git">Git</span>
              <span data-word="etc.">etc.</span>
            </div>
          </div>
        </div>
        <div class="skill_left" style={`background-image: url(${profile})`} />
      </div>
    </div>
    <!-- 🔥🔥🔥 ExperienceSection 🔥🔥🔥 -->
    <section class="experience_section">
      <div class="experience_fullstack_engineer_ctr">
        <svg viewBox="0 0 800 800" xmlns="http://www.w3.org/2000/svg" class="experience_svg" preserveAspectRatio="none">
          <defs>
            <linearGradient id="rainbow" x1="0" x2="0" y1="0" y2="100%" gradientUnits="userSpaceOnUse">
              <stop stop-color="#FF5B99" offset="0%" />
              <stop stop-color="#FF5447" offset="5%" />
              <stop stop-color="#FF7B21" offset="10%" />
              <stop stop-color="#EAFC37" offset="30%" />
              <stop stop-color="#4FCB6B" offset="40%" />
              <stop stop-color="#51F7FE" offset="50%" />
            </linearGradient>
          </defs>
          <mask id="m">
            <g class="experience_cloud1">
              <rect fill="#fff" width="100%" height="801" y="799" />
              <image xlink:href="https://assets.codepen.io/721952/cloud1Mask.jpg" width="1200" height="800" />
            </g>
          </mask>
          <text fill="url(#rainbow)">
            <tspan x="50%" y="5%" dominant-baseline="middle" text-anchor="middle"> I'M AN </tspan>
            <tspan x="50%" y="15%" dominant-baseline="middle" text-anchor="middle"> EXPERIENCED </tspan>
          </text>
          <text fill="#fff" x="50%" y="25%" dominant-baseline="middle" text-anchor="middle">FULL STACK ENGINEER</text>
          <g mask="url(#m)">
            <rect fill="#fff" width="100%" height="100%" />
            <text x="50%" y="25%" dominant-baseline="middle" text-anchor="middle" fill="#000" class="experience_f_text_back">FULL STACK ENGINEER</text>
          </g>
        </svg>
      </div>
      <section class="experience_hero_section" bind:offsetHeight={experience} id="time_line_id">
        <div class="experience_time_line">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 600" class="experience_time_line_svg" preserveAspectRatio="none">
            <path class="experience_line01 experience_line" d="M 245 100 265 100" />
            <path class="experience_line02 experience_line" d="M 245 200 265 200" />
            <path class="experience_line03 experience_line" d="M 245 300 265 300" />
            <path class="experience_line04 experience_line" d="M 245 400 265 400" />
            <path class="experience_line05 experience_line" d="M 245 500 265 500" />
            <text class="experience_first experience_txt experience_text01" x="175" y="100" text-anchor="end" dominant-baseline="middle" />
            <text class="experience_second experience_txt text01_1" x="300" y="100" text-anchor="start" dominant-baseline="middle">BSc (Hons) in IT</text>
            <text class="experience_last experience_txt text01_2" x="300" y="135" text-anchor="start" dominant-baseline="middle">@SLIIT</text>

            <text class="experience_first experience_txt experience_text02" x="175" y="200" text-anchor="end" dominant-baseline="middle">2015 - 2017</text>
            <text class="experience_second experience_txt text02_1" x="300" y="200" text-anchor="start" dominant-baseline="middle">Senior Software Engineer</text>
            <text class="experience_last experience_txt text02_2" x="300" y="235" text-anchor="start" dominant-baseline="middle">@Arit Co., Ltd</text>

            <text class="experience_first experience_txt experience_text03" x="175" y="300" text-anchor="end" dominant-baseline="middle">2017 - 2020</text>
            <text class="experience_second experience_txt text03_1" x="300" y="300" text-anchor="start" dominant-baseline="middle">Senior Software Engineer</text>
            <text class="experience_last experience_txt text03_2" x="300" y="335" text-anchor="start" dominant-baseline="middle">@Takumi Tech (pvt) Ltd</text>

            <text class="experience_first experience_txt experience_text04" x="175" y="400" text-anchor="end" dominant-baseline="middle">2020 - 2021</text>
            <text class="experience_second experience_txt text04_1" x="300" y="400" text-anchor="start" dominant-baseline="middle">Freelancer</text>
            <text class="experience_last experience_txt text04_2" x="300" y="435" text-anchor="start" dominant-baseline="middle">@WDA</text>

            <text class="experience_first experience_txt experience_text05" x="175" y="500" text-anchor="end" dominant-baseline="middle">From 2021</text>
            <text class="experience_second experience_txt text05_1" x="300" y="500" text-anchor="start" dominant-baseline="middle">Senior FullStack Engineer</text>
            <text class="experience_last experience_txt text05_2" x="300" y="535" text-anchor="start" dominant-baseline="middle">@Noon Lanka (pvt) Ltd</text>

            <path
              class="experience_theLine"
              d="M 210 0 C 233.709 62.871 262.885 -3.26 255 109.552 V 200 V 300 V 400 V 500 C 256 553 296 597 343 597"
              fill="none"
              stroke="#800000"
              stroke-width="5px"
              stroke-linecap="round"
            />

            <circle class="experience_ball experience_ball00" r="5" cx="50" cy="100" />
            <circle class="experience_ball experience_ball01" r="4" cx="255" cy="100" />
            <circle class="experience_ball experience_ball02" r="4" cx="255" cy="200" />
            <circle class="experience_ball experience_ball03" r="4" cx="255" cy="300" />
            <circle class="experience_ball experience_ball04" r="4" cx="255" cy="400" />
            <circle class="experience_ball experience_ball05" r="4" cx="255" cy="500" />
          </svg>
        </div>
        <div class="experience_hero_ctr">
          <img src={hero} alt="hero" class="experience_hero_img" id="experience_hero_img" />
          <!-- <div id="mask" class="experience_mask_ctr" style={`background-image: url(${hero}); -webkit-mask-image: url(${inkmask}); mask-image: url(${inkmask});`} /> -->
          <img src={fire} alt="fire" class="experience_fire" />
        </div>
      </section>
    </section>
    <!-- 🔥🔥🔥 FooterSection 🔥🔥🔥 -->
    <div class="extra_padding" />
    <div class="footer_rounded_div" style="height: {curveValue}vh">
      <div class="footer_rounded_div_inner" />
    </div>
    <section class="footer_section">
      <div class="footer_inner">
        <div class="footer_left">
          <div class="footer_social">
            <div class="footer_social_copy">FIND MORE ABOUT ME</div>
            <div class="footer_social_icon_outer">
              <div class="footer_social_icon_ctr"><img src={github} alt="" class="footer_social_icon" /></div>
              <div class="footer_social_icon_ctr"><img src={codepen} alt="" class="footer_social_icon" /></div>
              <div class="footer_social_icon_ctr"><img src={medium} alt="" class="footer_social_icon" /></div>
              <div class="footer_social_icon_ctr"><img src={youtube} alt="" class="footer_social_icon" /></div>
              <div class="footer_social_icon_ctr"><img src={linkedin} alt="" class="footer_social_icon" /></div>
            </div>
          </div>
          <div class="footer_contacts">
            <div class="footer_contacts_copy">CONTACTS</div>
            <div class="footer_contacts_desc">
              <div class="footer_contacts_desc_item">
                <div class="footer_desc_item_left">EMAIL:</div>
                <div class="footer_desc_item_right">duminda.g.k@gmail.com</div>
              </div>
              <div class="footer_contacts_desc_item">
                <div class="footer_desc_item_left">PHONE:</div>
                <div class="footer_desc_item_right">+94765742200</div>
              </div>
              <div class="footer_contacts_desc_item">
                <div class="footer_desc_item_left">ADDRESS:</div>
                <div class="footer_desc_item_right">296/B, Motemulla, Yogiyana, Sri Lanka</div>
              </div>
            </div>
          </div>
        </div>
        <div class="footer_right">
          <div class="footer_connect_copy">LET'S CONNECT</div>
          <div class="footer_connect_desc">I do digital design, brand design, and art direction. Send Me an Email</div>
          <form class="footer_email_ctr">
            <div class="footer_input_group">
              <label for="email">Email:</label>
              <input type="text" class="footer_input_email" name="email" placeholder="Enter Your Email Here" />
            </div>
            <div class="footer_input_group">
              <label for="message">Message:</label>
              <textarea name="message" rows="10" cols="30" placeholder="Enter Your Message Here" class="footer_input_textarea" />
            </div>
            <button on:click={handleClick} type="button" class="footer_email_btn">SUBMIT</button>
          </form>
        </div>
      </div>
      <div class="footer_rights">@2023 Duminda Kodagoda. All Rights Reserved.</div>
    </section>
  </div>
</section>
