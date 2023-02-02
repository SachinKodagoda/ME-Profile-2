<section class="experience">
  <svg viewBox="0 0 1200 800" xmlns="http://www.w3.org/2000/svg" class="experience_svg">
    <mask id="m">
      <g class="cloud1">
        <rect fill="#fff" width="100%" height="801" y="799" />
        <image
          xlink:href="https://assets.codepen.io/721952/cloud1Mask.jpg"
          width="1200"
          height="800"
        />
      </g>
    </mask>
    <text fill="#fff" x="50%" y="40%" dominant-baseline="middle" text-anchor="middle">
      EXPLORE
    </text>
    <g mask="url(#m)">
      <rect fill="#fff" width="100%" height="100%" />
      <text x="50%" y="40%" dominant-baseline="middle" text-anchor="middle" fill="#162a43">
        FURTHER
      </text>
    </g>
  </svg>
</section>

<style>
  .experience {
    min-height: calc(100vh + 8px);
    width: 100%;
    background: #000;
    font-size: 99px;
    font-weight: 900;
    text-align: center;
    position: relative;
  }
  .experience_svg {
    width: 100%;
    display: block;
  }
</style>
