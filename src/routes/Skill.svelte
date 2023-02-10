<script>
  import profile from '$lib/images/profile4.jpg';
</script>

<div class="skill">
  <div class="skill_inner">
    <div class="background_font">
      <span class="background_font_inner" data-word="FULLSTACK">FULLSTACK</span>
    </div>
    <div class="skill_left" style={`background-image: url(${profile})`} />
    <div class="skill_right">
      <div class="skill_right_inner">
        <div>
          <span data-word="Html,">Html,</span>
          <span data-word="CSS,">CSS,</span>
          <span data-word="JS">JS</span>
        </div>
        <div>
          <span data-word="React,">React,</span>
          <span class="word word_special" data-word="Next.js">
            Next.js
            <svg width="50" height="5" viewBox="0 0 50 5" fill="none" xmlns="http://www.w3.org/2000/svg" class="wave">
              <path
                d="M1 2C2.5 1.55556 5.2 1 8 1C11.5 1 13.5 3 16 3C18.5 3 21 1 23.5 1C26 1 26.5 3 33 3C39.5 3 37.5 2 41.5 1.33333C45 0.75 47.6667 1.55556 49.5 2"
                stroke="#8a0303"
                stroke-linecap="round"
                class="wave_path"
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
  </div>
</div>

<style>
  .skill {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    position: relative;
    min-height: 100vh;
    background: #000;
  }

  .skill_inner {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
    gap: 32px;
    padding: var(--gap-l);
    position: relative;
    flex-direction: column;
    font-size: var(--font2);
    line-height: 1.8;
  }

  @media only screen and (min-width: 1024px) {
    .skill_inner {
      flex-direction: row;
    }
  }

  .skill_left {
    background-position: center;
    background-repeat: no-repeat;
    border: 8px solid #fff;
    background-size: cover;
    display: block;
    max-width: 500px;
    width: 100%;
    aspect-ratio: 1/1;
    box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.5);
    border-radius: 32px;
    position: relative;
    z-index: 1;
  }

  .skill_right {
    border: 8px solid #111;
    font-weight: 200;
    border-radius: 32px;
    max-width: 500px;
    width: 100%;
    aspect-ratio: 1/1;
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.5);
    position: relative;
    background: #fff;
    padding: 16px;
  }

  .skill_right_inner {
    font-weight: 400;
    max-width: 400px;
  }

  .background_font {
    position: absolute;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    width: 100vw;
    height: 100%;
    font-weight: 900;
    white-space: nowrap;
    display: flex;
    align-items: center;
    overflow: hidden;
  }
  .background_font_inner {
    display: inline-block;
    font-size: 100vmin;
    vertical-align: bottom;
    color: transparent;
    position: relative;
    line-height: 1em;
    height: 1em;
  }

  .word {
    display: inline-block;
    position: relative;
    color: transparent;
    line-height: 1em;
    height: 1em;
  }

  .background_font_inner::before {
    content: attr(data-word);
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    color: transparent;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-image: linear-gradient(to top, var(--l-color1) 0%, var(--l-color2) calc(var(--progress) * 100%) calc(var(--progress) * 100%), var(--l-color3) calc(var(--progress) * 100%) 100%);
    background-size: cover;
    background-repeat: no-repeat;
  }

  .wave {
    position: absolute;
    left: 0;
    bottom: 0;
    display: block;
    width: 100%;
    height: auto;
    transform: translateY(100%);
  }

  @keyframes wave {
    to {
      d: path(
        'M1 2.0665C3.16667 2.5665 8 3.3665 10 2.5665C12.5 1.5665 12.5 0.566505 15 1.56651C16.857 2.3093 21.5 0.566511 23.5 1.5665C25.3439 2.48844 25 2.06651 27.5 2.56651C30 3.06651 32.5 0.566497 35 1.0665C37.5 1.5665 41 3.56648 43 3.0665C44.6 2.66651 48 2.23318 49.5 2.06651'
      );
    }
  }

  .wave_path {
    -webkit-animation: wave 0.4s ease-in-out infinite alternate;
    animation: wave 0.4s ease-in-out infinite alternate;
    -webkit-animation-delay: -0.25s;
    animation-delay: -0.25s;
  }

  .word_special {
    color: #8a0303;
    font-weight: 900;
  }
</style>
