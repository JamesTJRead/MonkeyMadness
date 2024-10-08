<footer id="contact">
  <p>&copy; 2023 Monkey Madness Training. All rights reserved.</p>
  <nav>
    <a href="#">Privacy Policy</a>
    <a href="#">Terms of Use</a>
    <a href="#">Contact Us</a>
  </nav>
</footer>

<style>
  footer {
    background-color: #111;
    color: #888;
    text-align: center;
    padding: 30px 0;
    font-size: 14px;
    position: relative;
    overflow: hidden;
  }

  footer::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 2px;
    background: linear-gradient(90deg, #3E7490, #7EB9BD, #3E7490);
    animation: rainbow 5s linear infinite;
  }

  @keyframes rainbow {
    0% {
      background-position: 0% 50%;
    }
    100% {
      background-position: 100% 50%;
    }
  }

  nav {
    margin-top: 20px;
  }

  a {
    color: #888;
    text-decoration: none;
    margin: 0 15px;
    transition: all 0.3s ease;
    position: relative;
  }

  a::after {
    content: '';
    position: absolute;
    bottom: -5px;
    left: 0;
    width: 100%;
    height: 2px;
    background-color: #7EB9BD;
    transform: scaleX(0);
    transition: transform 0.3s ease;
  }

  a:hover {
    color: #fff;
  }

  a:hover::after {
    transform: scaleX(1);
  }
</style>