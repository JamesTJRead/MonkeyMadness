<script>
  const sections = [
    {
      title: "STRENGTH TRAINING",
      content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
      image: "https://source.unsplash.com/random/800x600?weightlifting"
    },
    {
      title: "CARDIO BLAST",
      content: "Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
      image: "https://source.unsplash.com/random/800x600?running"
    },
    {
      title: "NUTRITION PLANS",
      content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
      image: "https://source.unsplash.com/random/800x600?healthy-food"
    }
  ];
</script>

<section class="alternating-content">
  {#each sections as section, index}
    <div class="content-section" class:right={index % 2 !== 0}>
      <div class="text-content">
        <h2>{section.title}</h2>
        <p>{section.content}</p>
        <a href="#" class="learn-more">LEARN MORE</a>
      </div>
      <div class="image-content" style="background-image: url('{section.image}')"></div>
    </div>
  {/each}
</section>

<style>
  .alternating-content {
    background-color: #000;
    padding: 50px 0;
  }

  .content-section {
    display: flex;
    align-items: center;
    margin-bottom: 50px;
  }

  .content-section.right {
    flex-direction: row-reverse;
  }

  .text-content {
    flex: 1;
    padding: 0 50px;
  }

  .image-content {
    flex: 1;
    height: 400px;
    background-size: cover;
    background-position: center;
    border-radius: 10px;
    box-shadow: 0 0 20px rgba(255, 69, 0, 0.3);
  }

  h2 {
    font-size: 36px;
    color: #ff4500;
    margin-bottom: 20px;
    text-transform: uppercase;
    letter-spacing: 2px;
  }

  p {
    font-size: 18px;
    color: #ddd;
    margin-bottom: 20px;
    line-height: 1.6;
  }

  .learn-more {
    display: inline-block;
    background-color: #ff4500;
    color: #fff;
    padding: 10px 20px;
    text-decoration: none;
    font-weight: bold;
    border-radius: 5px;
    transition: all 0.3s ease;
  }

  .learn-more:hover {
    background-color: #ff6347;
    transform: translateY(-3px);
    box-shadow: 0 5px 15px rgba(255, 69, 0, 0.4);
  }

  @media (max-width: 768px) {
    .content-section, .content-section.right {
      flex-direction: column;
    }

    .text-content {
      padding: 30px;
    }

    .image-content {
      width: 100%;
      margin-top: 30px;
    }
  }
</style>