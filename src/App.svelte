<script>
  import Header from './components/Header.svelte';
  import Hero from './components/Hero.svelte';
  import Features from './components/Features.svelte';
  import Programs from './components/Programs.svelte';
  import AlternatingContent from './components/AlternatingContent.svelte';
  import Footer from './components/Footer.svelte';
</script>

<main>
  <Header />
  <Hero />
  <Features />
  <Programs />
  <AlternatingContent />
  <Footer />
</main>

<style>
  :global(body) {
    margin: 0;
    padding: 0;
    font-family: 'Roboto', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    background-color: #000;
    color: #fff;
  }

  main {
    max-width: 100%;
    margin: 0 auto;
  }
</style>