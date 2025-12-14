<template>
    <section class="section food" style="margin-top: 50px;">
      <div class="container">
        <p class="eyebrow">Our Food</p>
        <!-- Header -->
        <header class="food-header">
          <h2>Comfort Food, Properly Done</h2>
          <p class="lede">
            Evenings feature <strong>Callum Davis</strong> and his delicious home-cooked recipes —
            seasonal, honest, and made for slow and thoughtful conversations.
          </p>
        </header>
  
        <!-- Feature row: image + copy -->
        <div class="feature card">
          <figure class="feature-media">
            <img
              src="@/assets/callum.jpg"
              alt="Warm plated dish on wood"
              loading="lazy"
            />
          </figure>
          <div class="feature-copy">
            <h3>What's in Store For You?</h3>
            <p>
              Rotating dishes with soulful basics. think baked vegetables, braised proteins,
              and a bright, herb-forward finish. It's the type of stuff that truly makes you believe it was cooked with love and precision, the kind of plate that makes you want to make it yourself in your own abode.
            </p>
            <p>
             Callum is heavily inspired by the likes of Gordan Ramsay, Marco Pierre and Sat Baines.
            </p>
            <ul class="bullets">
              <li>Locally sourced where possible</li>
              <li>Not a single part of Callum's dishes include added preservatives or nasty ingredients companies hope you overlook</li>
              <li>Healthy, simple and delicious... What else can one ask for?</li>
            </ul>
          </div>

        </div>
  
        <!-- Recipe cards -->
        <div class="recipes">
          <article class="card recipe">
            <img src="" alt="Dish 1" loading="lazy" />
            <div class="meta">
              <h4>Two Day Spaghetti Bolognaise</h4>
              <p>Thick, beautifully seasoned and rich sauce sat atop a mountain of pasta</p>
            </div>
          </article>
  
          <article class="card recipe">
            <img src="@/assets/orzo.PNG" alt="Dish 2" loading="lazy" />
            <div class="meta">
              <h4>Lemon Orzo</h4>
              <p></p>
            </div>
          </article>
          <article class="card recipe">
            <img src="" alt="Dish 3" loading="lazy" />
            <div class="meta"> 
              <h3>Dessert</h3>
              <h4>Sticky Date Pudding</h4>
              <p>Seductive, pleasing and moist... much like my ex piece. Hook into our delightful sticky date pudding to end the evening, at our venue at least...</p>
            </div>
          </article>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>

</script>
  
  <style scoped>
  .food-header {
    color: bisque;
    text-align: center;
    margin-bottom: 20px;
  }
  .food-header h2 {
    margin: 0 0 8px;
    font-size: clamp(28px, 4vw, 42px);
  }
  .lede {
    margin: 0;
    opacity: 0.9;
    max-width: 65ch;
    margin-inline: auto;
  }
  
  .eyebrow {
    text-align: center;
    text-transform: uppercase;
    opacity: 0.7;
    letter-spacing: 2px;
    margin: 0 0 8px;
    font-size: 0.85rem;
    color: bisque;
  }

  /* Feature */
  .feature {
    text-align: center;
    color: bisque;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 22px;
    padding: 16px;
    border-radius: 16px;
    margin-top: 18px;
  }

  .feature-media {
  display: flex;
  justify-content: center;
  align-items: center;
}

.feature-media img {
  width: 100%;
  height: auto;
  max-width: 550px;     /* hard upper limit */
  max-height: 400px;    /* hard upper limit */
  object-fit: cover;    /* keep aspect ratio */
  border-radius: 16px;
  border: 1px solid rgba(255,255,255,0.08);
  box-shadow: 0 8px 20px rgba(0,0,0,0.25);
}
  .feature-copy h3 {
    margin: 0 0 6px;
    font-size: clamp(20px, 3vw, 28px);
  }
  .feature-copy p { margin: 0 0 10px; opacity: .9; }
  .bullets {
    padding-left: 18px;
    margin: 0 0 12px;
    opacity: .9;
    list-style: none;
  }
  
  /* Recipes grid */
  .recipes {
    margin: 20px;
    color: bisque;
    margin-top: 18px;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 14px;
  }
  .recipe {
    overflow: hidden;
    border-radius: 14px;
  }
  .recipe img {
    width: 100%; height: 160px; object-fit: cover; display: block;
  }
  .recipe .meta { padding: 12px; }
  .recipe h4 { margin: 0 0 6px; font-size: 1.05rem; }
  .recipe p { margin: 0; opacity: .85; }
  
  /* Responsive: stack feature row */
  @media (max-width: 900px) {
    .feature { grid-template-columns: 1fr; }
  }
  </style>
  