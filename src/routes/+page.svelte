<script lang="ts">
  import ai from '$lib/images/ai2.mp4';
  import back2 from '$lib/images/back5.jpg';
  import back from '$lib/images/back6.jpeg';
  import cloud from '$lib/images/cloud6.png';
  import logo from '$lib/images/dk-logo.svg';
  import download from '$lib/images/download.svg';
  import fire from '$lib/images/fire.gif';
  import codepen from '$lib/images/icon-codepen.svg';
  import github from '$lib/images/icon-github.svg';
  import linkedin from '$lib/images/icon-linkedin.svg';
  import medium from '$lib/images/icon-medium.svg';
  import youtube from '$lib/images/icon-youtube.svg';
  import leftCorner from '$lib/images/left_corner.svg';
  import logo_angular from '$lib/images/logo-angular.svg';
  import logo_css from '$lib/images/logo-css.svg';
  import logo_html from '$lib/images/logo-html.svg';
  import logo_java from '$lib/images/logo-java.svg';
  import logo_javascript from '$lib/images/logo-javascript.svg';
  import logo_next from '$lib/images/logo-next.svg';
  import logo_php from '$lib/images/logo-php.svg';
  import logo_python from '$lib/images/logo-python.svg';
  import logo_react from '$lib/images/logo-react.svg';
  import logo_svelte from '$lib/images/logo-svelte.svg';
  import logo_ux from '$lib/images/logo-ux.svg';
  import logo_vue from '$lib/images/logo-vue.svg';
  import hero from '$lib/images/main.jpg';
  import menu from '$lib/images/menu.svg';
  import profile from '$lib/images/profile1.jpg';
  import scroll from '$lib/images/scroll.svg';
  import v1 from '$lib/images/v1.jpg';
  import v2 from '$lib/images/v2.jpg';
  import v3 from '$lib/images/v3.jpg';
  import v4 from '$lib/images/v4.jpg';
  import video1 from '$lib/images/video1.mp4';
  import video2 from '$lib/images/video2.mp4';
  import video3 from '$lib/images/video3.mp4';
  import video4 from '$lib/images/video4.mp4';
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

    // 🔥🔥🔥 Section 2 - TechStack 🔥🔥🔥 -->
    gsap.fromTo(
      '.skill_background_font_inner',
      { xPercent: 100 },
      {
        xPercent: -100,
        scrollTrigger: {
          trigger: '.skill_background_font_inner',
          scrub: true
        }
      }
    );

    // 🔥🔥🔥 Section 3 - I'M 🔥🔥🔥 -->
    gsap
      .timeline({
        defaults: { duration: 1, autoAlpha: 1 },
        scrollTrigger: {
          trigger: '.experience_section_top',
          scrub: true,
          pin: true,
          start: 'top top',
          end: 'bottom top'
        }
      })
      .to('.experience_section_top', { duration: 0.01, autoAlpha: 0.1 });

    // 🔥🔥🔥 Section 4 - Work 🔥🔥🔥 -->
    gsap.fromTo(
      '.pin_content_1',
      { xPercent: 0 },
      {
        xPercent: -33,
        scrollTrigger: {
          trigger: '.pin_content_1',
          scrub: true,
          start: 'top bottom',
          end: 'bottom top'
        }
      }
    );
    gsap.fromTo(
      '.pin_content_2',
      { xPercent: -33 },
      {
        xPercent: 0,
        scrollTrigger: {
          trigger: '.pin_content_2',
          scrub: true,
          start: 'top bottom',
          end: 'bottom top'
        }
      }
    );

    // 🔥🔥🔥 Section 5 - Experience 🔥🔥🔥 -->
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

    //  🔥🔥🔥 Section6 - Footer 🔥🔥🔥 -->
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

<section id="smooth-wrapper" class="app">
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
        <div class="skill_left" style={`background-image: url(${back2})`}>
          <div class="skill_left_inner">
            <img src={logo_html} alt="react" class="skill_icon s_item1" />
            <img src={logo_css} alt="react" class="skill_icon s_item2" />
            <img src={logo_javascript} alt="react" class="skill_icon s_item3" />
            <img src={logo_react} alt="react" class="skill_icon s_item4" />
            <img src={logo_angular} alt="react" class="skill_icon s_item5" />
            <img src={logo_vue} alt="react" class="skill_icon s_item6" />
            <img src={logo_svelte} alt="react" class="skill_icon s_item7" />

            <img src={logo_next} alt="react" class="skill_icon s_item8" />

            <img src={logo_ux} alt="react" class="skill_icon s_item9" />

            <img src={logo_php} alt="react" class="skill_icon s_item10" />
            <img src={logo_java} alt="react" class="skill_icon s_item11" />
            <img src={logo_python} alt="react" class="skill_icon s_item12" />
            <div class="skill_word s_item13">
              <span>SPECIALIZED IN UX/UI &</span>
              <span class="skill_word_inner">
                NEXT.js
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
          </div>
        </div>
        <div class="skill_right" style={`background-image: url(${back2})`}>
          <div class="skill_right_video">
            <video class="skill_right_video" src={ai} loop muted autoplay />
          </div>
          <div class="skill_right_other">AI & Machine Learning</div>
          <div class="skill_right_interested">INTERESTED IN</div>
        </div>
      </div>
    </div>
    <!-- 🔥🔥🔥 ExperienceSection 🔥🔥🔥 -->
    <section class="experience_section_top">
      <div class="experience_section_top_title1">I'M AN</div>
      <div class="experience_section_top_title2">EXPERIENCED</div>
      <div class="experience_section_top_title3">FULL STACK ENGINEER</div>
    </section>
    <section class="experience_section">
      <div class="experience_fullstack_engineer_ctr">
        <img src={cloud} alt="cloud" class="experience_cloud" />
      </div>
      <!-- 🔥🔥🔥 PinSection 🔥🔥🔥 -->
      <div class="white_hider" />
      <section class="pin_section">
        <div class="pin_content pin_content_1">
          <div class="pin_box">
            <div class="pin_box_inner"><img class="pin_image" src={v1} alt="img" /></div>
          </div>
          <div class="pin_box">
            <div class="pin_box_inner"><video class="pin_video" src={video1} loop muted autoplay /></div>
          </div>
          <div class="pin_box">
            <div class="pin_box_inner"><img class="pin_image" src={v2} alt="img" /></div>
          </div>
          <div class="pin_box">
            <div class="pin_box_inner"><video class="pin_video" src={video2} loop muted autoplay /></div>
          </div>
        </div>

        <div class="pin_content pin_content_2">
          <div class="pin_box">
            <div class="pin_box_inner"><img class="pin_image" src={v4} alt="img" /></div>
          </div>
          <div class="pin_box">
            <div class="pin_box_inner"><video class="pin_video" src={video4} loop muted autoplay /></div>
          </div>
          <div class="pin_box">
            <div class="pin_box_inner"><img class="pin_image" src={v3} alt="img" /></div>
          </div>
          <div class="pin_box">
            <div class="pin_box_inner"><video class="pin_video" src={video3} loop muted autoplay /></div>
          </div>
        </div>
      </section>
      <section class="experience_hero_section" id="time_line_id">
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
