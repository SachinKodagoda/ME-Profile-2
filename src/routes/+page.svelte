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
  import logo_aws from '$lib/images/logo-aws.svg';
  import logo_css from '$lib/images/logo-css.svg';
  import logo_firebase from '$lib/images/logo-firebase.svg';
  import logo_html from '$lib/images/logo-html.svg';
  import logo_javascript from '$lib/images/logo-javascript.svg';
  import logo_mysql from '$lib/images/logo-mysql.svg';
  import logo_php from '$lib/images/logo-php.svg';
  import logo_python from '$lib/images/logo-python.svg';
  import logo_react from '$lib/images/logo-react.svg';
  import logo_svelte from '$lib/images/logo-svelte.svg';
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
  let angleVal = 0;
  let d: HTMLDivElement;

  function mouseHandler(e: MouseEvent) {
    if (!d || !e) return;
    const mouseX = e?.clientX;
    const mouseY = e?.clientY;
    const rect = d?.getBoundingClientRect();
    const anchorX = rect.left + rect.width / 2;
    const anchorY = rect.top + rect.height / 2;
    const angleDeg = angle(mouseX, mouseY, anchorX, anchorY);
    angleVal = 90 + angleDeg;
  }

  function angle(cx: number, cy: number, ex: number, ey: number) {
    const dy = ey - cy;
    const dx = ex - cx;
    const theta = Math.atan2(dy, dx); // range (-PI, PI]
    const deg = (theta * 180) / Math.PI; // rads to degree, range (-180, 180]
    return deg;
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
        <div class="skill_safer">
          <div class="skill_left" style={`background-image: url(${back2})`}>
            <div class="skill_left_inner">
              <img src={logo_html} alt="react" class="skill_icon s_item1" />
              <img src={logo_css} alt="react" class="skill_icon s_item2" />
              <img src={logo_javascript} alt="react" class="skill_icon s_item3" />
              <img src={logo_react} alt="react" class="skill_icon s_item4" />
              <img src={logo_angular} alt="react" class="skill_icon s_item5" />
              <img src={logo_vue} alt="react" class="skill_icon s_item6" />
              <img src={logo_svelte} alt="react" class="skill_icon s_item7" />
              <img src={logo_python} alt="react" class="skill_icon s_item8" />
              <img src={logo_php} alt="react" class="skill_icon s_item9" />
              <img src={logo_aws} alt="react" class="skill_icon s_item10" />
              <img src={logo_mysql} alt="react" class="skill_icon s_item11" />
              <img src={logo_firebase} alt="react" class="skill_icon s_item12" />
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
          <div class="gopher">
            <svg width="1839" height="2500" viewBox="0 0 1839 2500" fill="none" xmlns="http://www.w3.org/2000/svg" class="gopher_img">
              <path
                d="M26.4784 1351.7C30.0558 1425.4 103.759 1391.06 136.675 1368.16C168.16 1345.98 177.463 1364.58 180.322 1321.64C182.47 1293.03 185.329 1265.12 183.9 1236.5C135.956 1232.2 84.4356 1243.65 45.0767 1272.27C24.3305 1286.58 -12.8805 1333.81 26.4712 1351.7M1495.53 2257.6C1552.06 2292.67 1655.82 2398.57 1570.66 2450.09C1489.09 2524.52 1443.3 2367.8 1371.74 2346.33C1402.5 2304.12 1441.14 2265.48 1495.53 2257.6ZM483.721 2377.1C417.172 2387.12 379.961 2447.23 324.152 2478C271.913 2508.77 251.878 2467.98 247.582 2459.4C239.716 2455.82 240.427 2462.97 227.547 2450.09C178.893 2373.52 277.638 2317.71 329.159 2279.79C400.715 2265.48 445.799 2327.73 483.721 2377.1ZM1809.66 1342.4C1806.08 1416.1 1732.38 1381.76 1699.47 1358.86C1667.98 1336.67 1658.68 1355.28 1655.82 1312.34C1653.66 1283.72 1650.8 1255.81 1652.24 1227.19C1700.18 1222.9 1751.7 1234.35 1791.06 1262.97C1811.1 1277.28 1849.02 1324.51 1809.66 1342.4Z"
                fill="#F6D2A2"
              />
              <path
                d="M1614.31 443.652C1869.77 353.491 1670.13 3.58485 1447.58 158.14C1301.61 32.9155 1100.54 10.0142 889.444 10.0142C682.657 26.4861 485.87 64.4083 348.483 184.619C126.647 41.4999 -77.9994 384.969 182.463 471.56C109.478 754.917 192.477 1044.01 181.027 1332.38C170.294 1591.42 102.316 1938.46 246.146 2171.02C368.511 2369.95 631.833 2440.79 848.655 2448.66C1125.58 2458.68 1461.17 2390.7 1595.7 2122.36C1724.5 1866.91 1688.73 1548.48 1672.27 1272.99C1655.81 994.634 1686.58 711.988 1614.3 443.645L1614.31 443.652Z"
                fill="#F6D2A2"
              />
              <path
                d="M1828.98 1298.75C1821.82 1283.72 1808.23 1266.55 1795.35 1257.24C1762.44 1233.63 1720.21 1220.75 1676.56 1219.32C1675.13 1174.96 1673.71 1126.29 1673.71 1064.76V1008.94C1672.99 832.916 1670.84 755.635 1660.83 659.03C1652.95 583.186 1640.78 513.059 1623.61 447.229C1681.58 425.046 1719.5 388.553 1734.53 341.321C1748.84 297.674 1741.68 248.301 1717.36 204.653C1692.31 161.717 1652.24 129.513 1605.73 116.64C1555.64 103.041 1501.26 113.062 1449.02 148.118C1402.5 108.767 1348.84 78.7104 1288.73 55.8091C1182.11 16.4646 1058.32 1.43652 890.162 1.43652V8.59138L889.444 1.43652C709.839 15.7462 576.742 43.6545 466.546 97.3231C422.18 118.788 382.828 144.548 348.483 174.604C295.526 141.689 240.428 133.816 189.625 149.562C142.4 163.872 101.612 197.506 77.2809 241.153C52.9501 284.801 47.2248 334.892 63.6824 377.828C80.14 420.757 118.062 454.391 174.597 475.144C156.71 547.411 147.407 623.981 145.978 708.417C144.541 790.705 148.118 856.543 160.999 1005.37C170.301 1116.29 173.879 1167.09 175.315 1228.63C126.654 1226.48 77.9993 1239.36 41.4994 1265.84C28.6192 1275.15 14.3095 1291.6 7.87303 1307.34C-1.42973 1327.38 2.1477 1345.27 20.7532 1356C23.6123 1390.35 42.9361 1406.09 72.2739 1403.23C93.7385 1401.08 119.499 1389.63 141.682 1373.89C146.368 1370.5 151.407 1367.62 156.71 1365.31C158.858 1364.59 160.287 1363.87 162.435 1363.15C162.435 1363.15 166.724 1361.73 168.161 1361.01C170.301 1360.29 172.449 1359.57 173.879 1358.14C172.449 1391.78 169.59 1426.84 163.146 1506.99C155.992 1597.14 152.414 1646.52 150.985 1701.62C144.541 1906.27 168.872 2055.1 241.857 2173.17C264.758 2210.38 292.667 2243.3 325.582 2273.36C319.138 2277.64 291.948 2297.69 283.364 2304.12C253.308 2327.02 232.561 2346.34 220.392 2367.81C204.653 2395.71 204.653 2423.62 222.54 2452.96L223.259 2453.68L223.977 2454.4C231.843 2462.26 236.139 2464.41 241.864 2464.41H243.998C244.716 2465.85 245.434 2466.56 246.153 2467.99C248.294 2471.57 250.441 2474.42 252.589 2477.29C270.476 2498.04 295.518 2503.05 329.152 2483.02C347.039 2473.71 359.919 2462.97 387.109 2440.08L388.546 2438.64C432.194 2401.44 453.658 2387.85 485.862 2382.83L497.313 2380.69C501.601 2382.84 505.897 2384.27 510.904 2386.41C612.516 2427.2 730.578 2449.38 850.085 2453.68C1004.65 2459.4 1153.48 2440.08 1279.42 2394.28C1313.05 2382.12 1344.54 2367.81 1374.59 2352.07C1393.2 2359.22 1408.93 2374.25 1439 2409.31C1440.43 2410.75 1440.43 2410.75 1441.14 2412.17C1442.57 2413.61 1442.57 2414.33 1443.29 2415.04C1444.71 2417.19 1446.86 2418.62 1448.29 2420.76C1471.91 2448.66 1487.66 2462.26 1505.54 2470.14C1529.15 2480.15 1552.05 2475.14 1575.66 2453.68C1617.17 2427.92 1620.03 2387.85 1592.83 2342.05C1573.52 2309.85 1539.89 2276.21 1508.4 2254.75C1545.61 2218.26 1577.81 2174.61 1602.85 2125.23C1671.55 1987.84 1698.03 1827.56 1696.6 1621.47C1695.88 1548.49 1693.01 1484.81 1685.15 1363.15V1359.58C1688.73 1361.01 1692.3 1363.16 1695.88 1366.02C1718.06 1381.05 1743.82 1393.21 1765.29 1395.36C1794.63 1398.22 1813.95 1382.48 1816.81 1348.13C1834.7 1336.68 1838.27 1318.79 1828.97 1298.76L1828.98 1298.75ZM1601.44 131.661C1644.37 143.111 1681.59 173.168 1704.48 213.238C1727.38 253.308 1733.82 298.392 1720.94 338.462C1707.35 380.68 1672.99 414.314 1619.33 434.349C1608.62 396.038 1595.97 358.301 1581.4 321.286C1602.16 303.399 1612.17 281.216 1595.71 249.737C1579.26 218.245 1550.64 214.667 1521.29 223.97C1502.69 199.639 1481.94 178.174 1460.47 158.139C1507.7 128.083 1556.36 119.499 1601.44 131.661ZM75.8586 373.525C60.8305 334.877 65.8374 289.089 88.7387 249.019C111.633 208.942 148.844 177.463 193.21 164.583C239.005 150.985 288.378 157.421 337.04 186.048C308.901 211.339 283.913 239.93 262.618 271.202C225.407 251.878 187.484 248.301 166.02 287.652C143.837 329.878 169.597 356.349 206.09 376.384C201.083 388.553 196.069 401.433 191.78 414.314C186.766 430.053 181.759 446.51 177.47 462.968C125.231 442.933 90.8866 412.166 75.8586 373.525ZM162.442 1348.84C161.724 1348.84 157.428 1350.27 157.428 1350.98C155.288 1351.7 153.14 1352.42 150.992 1353.85C145.266 1356 139.541 1359.57 133.823 1363.86C113.781 1378.18 89.4499 1388.91 70.8444 1390.34C49.3798 1392.49 37.218 1383.19 35.0701 1357.43C50.0982 1352.42 56.5347 1348.84 62.26 1340.26L50.8094 1331.67C46.5208 1337.39 42.225 1339.54 29.3448 1343.83C28.6264 1343.83 28.6264 1343.83 27.9081 1344.55C16.4646 1338.1 14.3167 1328.09 20.7604 1313.78C26.4857 1300.9 39.3659 1285.87 50.0982 1278C84.443 1252.96 130.238 1240.79 176.034 1243.65C176.034 1261.54 176.752 1279.43 176.034 1296.6C176.034 1298.75 176.034 1300.18 175.315 1302.33C174.604 1312.34 174.604 1316.64 173.886 1321.65C171.745 1342.4 170.308 1345.26 162.442 1348.84ZM378.539 2428.62L377.103 2430.06C350.631 2452.95 337.751 2462.26 321.293 2471.56C294.103 2488.02 275.498 2484.44 262.618 2468.7C260.47 2466.54 259.04 2463.69 257.611 2461.54C256.892 2460.82 256.174 2459.4 255.463 2458.68V2457.96C256.899 2445.08 261.906 2435.78 274.787 2415.74C275.505 2415.02 275.505 2415.02 275.505 2414.31C283.371 2402.86 286.948 2396.43 290.526 2388.55L277.646 2382.83C274.787 2389.27 271.209 2395 264.047 2406.44C263.329 2407.16 263.329 2407.16 263.329 2407.88C250.456 2426.48 244.723 2437.92 241.864 2450.8H241.146H238.998C237.561 2450.09 235.421 2448.66 232.561 2445.8C204.653 2401.43 226.836 2363.51 289.8 2316.28C297.674 2310.56 324.152 2291.95 331.307 2286.23C332.744 2286.23 334.166 2285.51 335.603 2284.79C374.236 2317.71 419.321 2346.33 469.412 2369.95C469.412 2370.66 470.13 2371.38 470.841 2372.1C441.503 2379.25 418.609 2394.28 378.539 2428.62ZM1579.97 2350.63C1602.16 2387.84 1601.44 2417.89 1573.53 2438.64C1571.39 2434.35 1569.95 2429.34 1567.09 2422.19C1567.09 2421.47 1567.09 2421.47 1566.38 2420.75C1556.36 2393.56 1549.92 2382.12 1537.76 2369.24L1527.73 2379.25C1538.47 2389.27 1543.48 2400 1553.5 2425.04C1553.5 2425.76 1553.5 2425.76 1554.21 2426.48C1557.79 2435.78 1559.94 2441.5 1562.09 2446.52C1543.48 2462.26 1527.02 2465.12 1509.85 2457.25C1494.82 2450.8 1480.51 2437.21 1457.61 2411.45C1456.18 2410.02 1454.75 2407.88 1453.32 2405.73C1452.6 2405.01 1451.88 2404.29 1451.16 2402.86C1449.74 2401.43 1449.74 2401.43 1449.02 2400C1422.55 2369.24 1406.81 2352.78 1389.63 2343.47C1429.71 2320.57 1465.49 2294.81 1497.69 2264.76C1527.73 2286.94 1561.37 2319.86 1579.97 2350.63ZM1589.99 2118.79C1528.45 2242.58 1419.69 2329.88 1273.71 2382.83C1149.2 2427.91 1001.8 2446.52 849.381 2440.79C586.77 2431.49 359.223 2339.9 252.604 2166.73C181.048 2051.52 157.428 1904.83 163.872 1703.04C166.02 1647.95 168.879 1598.57 176.034 1508.41C183.907 1406.8 186.055 1377.46 188.203 1331.67C189.632 1298.75 189.632 1265.12 188.921 1229.34C187.484 1166.37 183.907 1116.28 174.604 1003.94C161.724 855.099 158.147 789.98 159.576 708.403C161.731 601.08 176.034 506.616 206.09 417.18C254.73 271.906 344.187 173.872 472.989 110.196C581.038 57.2531 711.987 30.056 890.162 15.7391C1056.89 15.7391 1178.53 30.7671 1283.72 69.4077C1409.66 115.921 1503.4 197.491 1567.8 322.723C1609.3 424.327 1633.64 533.813 1646.52 659.748C1656.53 755.635 1658.68 832.916 1659.4 1008.22V1064.04C1660.11 1150.62 1661.54 1211.45 1665.12 1272.27C1666.55 1295.88 1667.26 1305.91 1670.84 1362.43C1678.71 1484.08 1681.58 1547.05 1682.29 1620.04C1683.73 1825.4 1657.97 1983.54 1589.99 2118.79ZM1808.95 1335.24C1808.23 1335.24 1807.52 1334.52 1806.81 1334.52C1793.93 1330.24 1789.63 1327.37 1785.34 1322.36L1773.89 1330.95C1780.33 1339.54 1786.77 1343.12 1801.08 1348.12C1798.22 1373.88 1786.06 1383.19 1765.31 1381.04C1746.71 1379.6 1722.37 1368.16 1702.33 1354.56C1696.61 1350.27 1690.89 1347.41 1685.16 1344.55C1684.44 1344.55 1683.73 1343.83 1683.01 1343.83C1680.15 1304.48 1680.15 1294.45 1678.72 1273.7L1676.57 1235.06C1716.65 1235.78 1756 1247.94 1786.05 1270.12C1796.79 1278 1809.67 1293.03 1815.39 1305.9C1822.55 1318.07 1821.12 1328.8 1808.95 1335.24Z"
                fill="black"
              />
              <path
                d="M997.93 747.978C998.649 784.47 1005.8 824.54 999.36 863.181C989.339 881.786 970.74 883.941 954.283 891.089C931.381 887.512 912.058 872.484 902.762 851.019C897.037 807.372 904.192 765.865 906.339 722.217C906.339 720.781 933.529 722.936 957.86 730.09C978.606 736.527 997.93 747.259 997.93 747.978ZM795.425 750.837C775.382 826.695 821.903 950.483 898.466 848.871C892.741 805.935 899.185 764.435 901.325 722.217C902.044 718.64 796.143 745.83 795.425 750.837Z"
                fill="white"
              />
              <path
                d="M1006.52 781.611C1005.08 760.139 1004.37 751.555 1004.37 740.822V735.815L999.361 734.379L909.199 706.478V701.463L899.896 703.618H899.178V704.33L797.573 730.09L793.996 730.808L792.559 734.379C776.82 772.308 780.397 829.554 800.432 864.617C823.334 904.687 860.538 905.398 898.467 859.603C903.752 869.803 911.363 878.617 920.686 885.331C930.008 892.044 940.779 896.47 952.128 898.251H954.283L956.424 897.532C959.29 896.096 962.149 895.377 967.164 893.237C967.882 893.237 967.882 893.237 968.593 892.518C989.339 885.363 997.931 879.638 1005.09 866.047L1005.8 865.328V863.899C1007.94 851.019 1008.66 837.42 1008.66 822.399C1008.66 811.66 1007.94 801.639 1006.52 781.611ZM892.023 755.132C891.305 768.012 890.594 773.019 889.882 780.174C888.446 806.653 888.446 826.688 890.601 846.723C856.96 889.659 830.489 889.659 812.601 857.455C795.425 827.406 791.841 776.597 804.728 742.97L894.882 720.069C894.171 729.372 893.46 738.674 892.023 755.132ZM992.206 861.04C987.199 869.624 980.755 873.92 963.579 879.645C962.861 879.645 962.861 879.645 962.149 880.356C957.861 881.793 954.995 883.215 952.847 883.934C933.523 880.356 917.072 867.476 909.199 849.589C907.051 830.265 907.051 810.23 908.481 783.759C909.199 776.597 909.199 771.59 910.636 758.709C912.058 742.259 912.777 732.238 912.777 722.935L990.776 746.548C990.776 755.85 991.494 764.435 992.924 783.04C994.353 802.364 995.065 812.378 995.065 823.829C995.065 837.42 994.346 849.589 992.206 861.04Z"
                fill="black"
              />
              <path d="M364.689 436.224C430.519 692.391 840.537 626.56 824.798 369.675C806.185 61.9799 301.725 121.374 364.689 436.224Z" fill="white" />
              <path
                d="M831.953 368.957C827.657 294.535 794.742 236.577 740.362 200.085C691.701 167.169 627.3 154.289 563.617 162.155C499.935 170.754 441.252 199.373 402.611 244.458C359.682 294.542 343.224 360.372 358.253 436.224C425.513 699.546 847.692 635.863 831.953 368.957ZM371.126 434.794C356.816 362.527 372.562 300.985 412.632 254.472C449.125 212.254 504.223 184.353 565.047 176.479C625.87 168.606 686.694 180.775 732.496 212.254C783.291 246.606 814.066 300.274 818.355 371.112C833.383 620.842 434.808 680.954 371.126 434.794Z"
                fill="black"
              />
              <path
                d="M477.752 469.139C516.085 469.139 547.16 435.501 547.16 394.006C547.16 352.511 516.085 318.873 477.752 318.873C439.419 318.873 408.344 352.511 408.344 394.006C408.344 435.501 439.419 469.139 477.752 469.139Z"
                fill="black"
                class="left-eye"
              />
              <path
                d="M509.23 430.491C518.319 430.491 525.688 421.843 525.688 411.175C525.688 400.506 518.319 391.858 509.23 391.858C500.141 391.858 492.772 400.506 492.772 411.175C492.772 421.843 500.141 430.491 509.23 430.491Z"
                fill="white"
                class="left-eye-ball"
              />
              <path d="M939.707 388.331C990.517 682.427 1471.37 604.428 1401.96 308.184C1339.71 41.9955 922.531 115.699 939.707 388.331Z" fill="white" />
              <path
                d="M1408.4 306.754C1344.72 32.6928 915.391 107.826 932.56 389.042V389.76C956.165 528.576 1079.97 599.421 1216.63 576.52C1278.88 565.787 1334.7 535.738 1371.19 491.372C1411.26 441.992 1425.57 378.31 1408.4 306.754ZM1360.46 482.781C1326.11 524.288 1273.88 552.907 1214.49 562.928C1084.97 584.393 969.045 517.844 946.151 387.613C930.405 122.854 1335.42 52.0094 1395.52 309.613C1411.27 377.591 1398.39 436.985 1360.46 482.781Z"
                fill="black"
              />
              <path
                d="M1057.78 450.584C1095.32 450.584 1125.76 416.946 1125.76 375.451C1125.76 333.956 1095.32 300.317 1057.78 300.317C1020.23 300.317 989.799 333.956 989.799 375.451C989.799 416.946 1020.23 450.584 1057.78 450.584Z"
                fill="black"
                class="right-eye"
              />
              <path
                d="M1089.26 411.936C1097.96 411.936 1105 403.288 1105 392.619C1105 381.951 1097.96 373.303 1089.26 373.303C1080.57 373.303 1073.52 381.951 1073.52 392.619C1073.52 403.288 1080.57 411.936 1089.26 411.936Z"
                fill="white"
                class="right-eye-ball"
              />
              <path
                d="M810.202 596.253C753.667 601.26 707.872 667.808 737.217 720.759C775.85 790.885 862.434 714.322 916.103 721.477C978.356 722.914 1029.17 787.307 1078.54 732.928C1133.64 672.815 1054.93 614.14 992.665 588.379L810.202 596.253Z"
                fill="#F6D2A2"
              />
              <path
                d="M1085.69 644.196C1066.37 619.865 1032.74 597.682 996.243 582.654L994.813 581.936H993.384L810.202 589.098C746.512 594.823 700.724 668.527 731.484 724.336C743.653 745.808 760.111 756.54 782.294 757.969C798.744 758.688 815.927 755.11 842.399 745.808C844.547 745.089 847.406 744.371 850.983 742.941C886.765 730.78 901.075 727.202 915.384 729.35H916.103C933.271 729.35 947.588 734.357 974.778 745.089C1004.83 757.251 1014.14 760.836 1029.16 762.258C1049.92 763.695 1067.81 756.54 1084.26 738.653C1112.16 707.878 1110.73 674.963 1085.69 644.196ZM1073.52 728.632C1059.93 743.66 1046.33 748.674 1029.88 747.956C1017 747.237 1008.41 743.66 979.785 732.209C951.166 720.047 935.426 715.759 916.821 715.04C898.934 712.885 883.906 716.47 845.976 729.35C842.399 730.78 839.54 731.498 837.392 732.209C785.153 750.096 760.111 748.667 742.935 717.181C717.175 670.674 756.533 607.703 810.202 602.696L991.236 595.534C1025.59 609.851 1056.36 630.597 1074.24 652.787C1095.71 678.541 1096.43 704.301 1073.52 728.632Z"
                fill="#231F20"
              />
              <path d="M1006.98 565.485C984.799 483.908 798.751 496.077 803.04 593.393C812.343 665.66 1028.45 646.337 1006.98 565.485Z" fill="black" />
            </svg>

            <div class="skill_stack">My Tech Stack</div>
          </div>
        </div>
        <div class="skill_right" style={`background-image: url(${back2})`}>
          <div class="skill_right_video">
            <video class="skill_right_video" src={ai} loop muted autoplay />
          </div>
          <div class="skill_right_other">AI & Machine Learning</div>
          <div class="skill_right_interested">A RESEARCH BY ME</div>
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
