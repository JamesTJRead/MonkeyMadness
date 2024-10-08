<section id="features" class="features">
  <div class="feature">
    <h2>INTENSE WORKOUTS</h2>
    <p>Push your limits</p>
  </div>
  <div class="feature">
    <h2>EXPERT TRAINERS</h2>
    <p>Learn from the best</p>
  </div>
  <div class="feature">
    <h2>24/7 SUPPORT</h2>
    <p>Train anytime</p>
  </div>
</section>

<style>
  .features {
    display: flex;
    justify-content: space-around;
    padding: 100px 0;
    background-color: #111;
    position: relative;
    overflow: hidden;
  }

  .features::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-image: linear-gradient(45deg, #3E7490 25%, transparent 25%), linear-gradient(-45deg, #3E7490 25%, transparent 25%), linear-gradient(45deg, transparent 75%, #3E7490 75%), linear-gradient(-45deg, transparent 75%, #3E7490 75%);
    background-size: 20px 20px;
    background-position: 0 0, 0 10px, 10px -10px, -10px 0px;
    opacity: 0.05;
  }

  .feature {
    text-align: center;
    max-width: 300px;
    padding: 30px;
    background-color: rgba(17, 17, 17, 0.8);
    border-radius: 10px;
    box-shadow: 0 0 20px rgba(126, 185, 189, 0.3);
    transition: all 0.3s ease;
  }

  .feature:hover {
    transform: translateY(-10px);
    box-shadow: 0 10px 30px rgba(126, 185, 189, 0.5);
  }

  h2 {
    font-size: 24px;
    margin-bottom: 15px;
    color: #7EB9BD;
    text-shadow: 0 0 10px rgba(126, 185, 189, 0.3);
  }

  p {
    font-size: 16px;
    color: #ddd;
    text-transform: uppercase;
    letter-spacing: 1px;
  }
</style>