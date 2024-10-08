<script>
  import { writable } from 'svelte/store';

  const cart = writable([]);

  const programs = [
    { id: 1, name: "Strength Training", price: 49.99, description: "8-week strength program" },
    { id: 2, name: "Cardio Blast", price: 39.99, description: "6-week high-intensity cardio" },
    { id: 3, name: "Nutrition Plan", price: 29.99, description: "4-week meal planning guide" },
  ];

  function addToCart(program) {
    cart.update(items => [...items, program]);
  }

  function removeFromCart(id) {
    cart.update(items => items.filter(item => item.id !== id));
  }

  $: cartTotal = $cart.reduce((total, item) => total + item.price, 0).toFixed(2);
</script>

<section id="programs" class="programs">
  <h2>OUR PROGRAMS</h2>
  <div class="program-list">
    {#each programs as program}
      <div class="program-card">
        <h3>{program.name}</h3>
        <p>{program.description}</p>
        <p class="price">${program.price}</p>
        <button on:click={() => addToCart(program)}>ADD TO CART</button>
      </div>
    {/each}
  </div>

  <div class="cart">
    <h3>Your Cart</h3>
    {#if $cart.length === 0}
      <p>Your cart is empty</p>
    {:else}
      <ul>
        {#each $cart as item}
          <li>
            {item.name} - ${item.price}
            <button on:click={() => removeFromCart(item.id)}>Remove</button>
          </li>
        {/each}
      </ul>
      <p>Total: ${cartTotal}</p>
      <button class="checkout-button">Proceed to Checkout</button>
    {/if}
  </div>
</section>

<style>
  .programs {
    background-color: #111;
    padding: 50px 0;
  }

  h2 {
    text-align: center;
    color: #7EB9BD;
    font-size: 36px;
    margin-bottom: 30px;
  }

  .program-list {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
  }

  .program-card {
    background-color: #222;
    border-radius: 10px;
    padding: 20px;
    margin: 10px;
    width: 300px;
    text-align: center;
    box-shadow: 0 0 20px rgba(126, 185, 189, 0.3);
    transition: all 0.3s ease;
  }

  .program-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 5px 30px rgba(126, 185, 189, 0.5);
  }

  .program-card h3 {
    color: #7EB9BD;
    margin-bottom: 10px;
  }

  .program-card p {
    color: #ddd;
    margin-bottom: 15px;
  }

  .program-card .price {
    font-size: 24px;
    font-weight: bold;
    color: #7EB9BD;
    margin-bottom: 15px;
  }

  button {
    background-color: #3E7490;
    color: #fff;
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }

  button:hover {
    background-color: #7EB9BD;
  }

  .cart {
    background-color: #222;
    border-radius: 10px;
    padding: 20px;
    margin-top: 30px;
    max-width: 500px;
    margin-left: auto;
    margin-right: auto;
  }

  .cart h3 {
    color: #7EB9BD;
    margin-bottom: 15px;
  }

  .cart ul {
    list-style-type: none;
    padding: 0;
  }

  .cart li {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 10px;
    color: #ddd;
  }

  .cart li button {
    background-color: #3E7490;
    color: #fff;
    border: none;
    padding: 5px 10px;
    border-radius: 3px;
    cursor: pointer;
    font-size: 12px;
  }

  .checkout-button {
    display: block;
    width: 100%;
    margin-top: 20px;
    padding: 15px;
    font-size: 18px;
    font-weight: bold;
    text-transform: uppercase;
  }
</style>