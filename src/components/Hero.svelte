<script>
  import { onMount } from 'svelte';

  let logoImg;

  onMount(() => {
    logoImg = new Image();
    logoImg.src = 'src/assets/MonkeyMadness_800x800.png';
  });
</script>

<section class="hero">
  <div class="hero-content">
    <img src={logoImg?.src} alt="MMT Logo" class="logo" />
    <p>WILL YOU JOIN ME?</p>
    <a href="#" class="cta-button">START TRAINING NOW</a>
  </div>
</section>

<style>
  .hero {
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    background-image: linear-gradient(135deg, #000 0%, #3E7490 100%);
    position: relative;
    overflow: hidden;
  }

  .hero-content {
    z-index: 1;
  }

  .logo {
    width: 800px;
    margin-bottom: 20px;
    transition: all 0.3s ease;

  }

  h1 {
    font-size: 48px;
    font-weight: 900;
    margin-bottom: 20px;
    text-shadow: 0 0 10px rgba(126, 185, 189, 0.7);
  }

  p {
    font-size: 24px;
    margin-bottom: 40px;
    text-transform: uppercase;
    letter-spacing: 2px;
  }

  .cta-button {
    background-color: #7EB9BD;
    color: #000;
    padding: 15px 30px;
    border-radius: 5px;
    text-decoration: none;
    font-size: 20px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 2px;
    transition: all 0.3s ease;
    position: relative;
    overflow: hidden;
  }

  .cta-button:hover {
    background-color: #3E7490;
    color: #fff;
    transform: scale(1.05);
    box-shadow: 0 0 20px rgba(126, 185, 189, 0.7);
  }

  @media (max-width: 768px) {
    h1 {
      font-size: 36px;
    }

    p {
      font-size: 18px;
    }


    .logo {
      width: 400px;
      margin-bottom: 20px;
    }

    .cta-button {
      font-size: 16px;
      padding: 12px 24px;
    }
  }
</style>