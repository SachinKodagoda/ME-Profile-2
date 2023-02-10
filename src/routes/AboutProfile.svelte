<script>
  import profile from '$lib/images/profile1.jpg';
</script>

<div class="about_inner_right">
  <div class="about_profile_ctr" id="about_profile_ctr" style={`background-image: url(${profile})`} />
</div>

<style>
  @keyframes fancy_border {
    0% {
      border-radius: 50% 50% 50% 50% / 50% 50% 50% 50%;
    }
    10% {
      border-radius: 46% 54% 51% 49% / 26% 24% 76% 74%;
    }
    20% {
      border-radius: 46% 54% 51% 49% / 72% 76% 24% 28%;
    }
    30% {
      border-radius: 50% 50% 50% 50% / 50% 50% 50% 50%;
    }
    40% {
      border-radius: 17% 83% 37% 63% / 20% 64% 36% 80%;
    }
    50% {
      border-radius: 84% 16% 76% 24% / 69% 27% 73% 31%;
    }
    60% {
      border-radius: 50% 50% 50% 50% / 50% 50% 50% 50%;
    }
    70% {
      border-radius: 18% 82% 84% 16% / 46% 49% 51% 54%;
    }
    80% {
      border-radius: 84% 16% 15% 85% / 42% 23% 77% 58%;
    }
    90% {
      border-radius: 22% 78% 34% 66% / 72% 24% 76% 28%;
    }
    100% {
      border-radius: 50% 50% 50% 50% / 50% 50% 50% 50%;
    }
  }

  .about_inner_right {
    width: var(--profile-img);
    aspect-ratio: 1/1;
  }

  .about_profile_ctr {
    width: 100%;
    height: 100%;
    background: #111;
    border-radius: 50%;
    overflow: hidden;
    background-position: center;
    background-repeat: no-repeat;
    border: 14px solid rgba(0, 0, 0, 0.3);
    border-radius: 50% 50% 50% 50%/50% 50% 50% 50%;
    transition: border-radius 400ms ease-in-out;
    background-size: 120% auto;
    -webkit-animation: fancy_border 12s ease-in-out infinite;
    animation: fancy_border 12s ease-in-out infinite;
    box-shadow: 0 0 8px 5px rgba(0, 0, 0, 0.1);
    outline: 10px solid #000;
  }
</style>
