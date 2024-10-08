<script>
  import { onMount } from 'svelte';
  let menuOpen = false;
  let logoImg;
  
  function toggleMenu() {
    menuOpen = !menuOpen;
  }

  onMount(() => {
    logoImg = new Image();
    logoImg.src = 'https://raw.githubusercontent.com/yourusername/your-repo/main/logo.png';
  });
</script>

<header>
  <nav class:open={menuOpen}>
    <div class="logo">
      <img src={logoImg?.src} alt="MMT Logo" />
    </div>
    <button class="menu-toggle" on:click={toggleMenu}>
      <span></span>
      <span></span>
      <span></span>
    </button>
    <ul class:open={menuOpen}>
      <li><a href="/">Home</a></li>
      <li><a href="#features">Programs</a></li>
      <li><a href="#trainers">Trainers</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>
</header>

<style>
  header {
    background-color: rgba(0, 0, 0, 0.9);
    backdrop-filter: blur(10px);
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 1000;
    padding: 10px 20px;
  }

  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .logo img {
    height: 40px;
    width: auto;
  }

  ul {
    display: flex;
    list-style-type: none;
  }

  li {
    margin: 0 15px;
  }

  a {
    color: #fff;
    text-decoration: none;
    font-size: 16px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 1px;
    transition: color 0.3s ease;
  }

  a:hover {
    color: #7EB9BD;
  }

  .menu-toggle {
    display: none;
  }

  @media (max-width: 768px) {
    .menu-toggle {
      display: block;
      background: none;
      border: none;
      cursor: pointer;
    }

    .menu-toggle span {
      display: block;
      width: 25px;
      height: 3px;
      background-color: #fff;
      margin: 5px 0;
      transition: 0.3s;
    }

    nav.open .menu-toggle span:nth-child(1) {
      transform: rotate(-45deg) translate(-5px, 6px);
    }

    nav.open .menu-toggle span:nth-child(2) {
      opacity: 0;
    }

    nav.open .menu-toggle span:nth-child(3) {
      transform: rotate(45deg) translate(-5px, -6px);
    }

    ul {
      display: none;
      flex-direction: column;
      position: absolute;
      top: 100%;
      left: 0;
      right: 0;
      background-color: rgba(0, 0, 0, 0.9);
      padding: 20px;
    }

    ul.open {
      display: flex;
    }

    li {
      margin: 10px 0;
    }
  }
</style>