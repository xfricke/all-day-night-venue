<template>
    <section class="section origin">
      <div class="container origin-wrap card">
  
        <!-- Image on top -->
        <figure class="origin-media">
          <img
            src="@/assets/coffee.JPG"
            alt="Seven Seeds banner"
            loading="lazy"
          />
        </figure>
  
        <!-- Text below -->
        <div class="origin-copy">
          <p class="eyebrow">Our Coffee</p>
          <h2>Proudly serving <span class="brand">Seven Seeds</span> coffee</h2>
          <p class="lede">
            Sourced with care, roasted by professionals. 
            Seven Seeds delivers bright, clean, balanced coffees that pair
            perfectly with our warm, cozy ambience.
          </p>
          <p>
            Whether you're here for a morning batch brew or a late-afternoon flat white,
            you're sipping on some of Melbourne's finest.
          </p>
        </div>
    
        <div class="seedsLogo">
            <img src="@/assets/sevenseeds.png"></img>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
  // no script needed for now
  </script>
  
  <style scoped>
  .origin-wrap {
    text-align: center;
    padding: 32px 24px;
    border-radius: 16px;
    color: bisque;
  }
  
  /* Image container */
  .origin-media {
    width: 100%;
    display: flex;
    justify-content: center;
    margin: 0 0 24px 0;
  }
  
  .origin-media img {
    width: 100%;
    max-width: 480px;        /* caps size on large monitors */
    max-height: 340px;       /* prevents it from becoming too tall */
    object-fit: cover;
    border-radius: 16px;
    border: 1px solid rgba(255,255,255,0.08);
    box-shadow: 0 6px 20px rgba(0,0,0,0.25);
  }
  
  /* Text styling */
  .eyebrow {
    text-transform: uppercase;
    opacity: 0.7;
    letter-spacing: 2px;
    margin: 0 0 8px;
    font-size: 0.85rem;
  }
  
  .origin-copy h2 {
    margin: 0 0 12px;
    font-size: clamp(28px, 4vw, 40px);
  }
  
  .origin-copy .lede {
    opacity: 0.9;
    max-width: 60ch;
    margin: 0 auto 12px auto;
  }
  
  .origin-copy p {
    max-width: 60ch;
    margin: 8px auto;
    opacity: 0.9;
  }
  
  .brand {
    color: var(--accent);
  }

  .seedsLogo img{
    margin-top: 50px;
    width: 200px;
    height: 200px;
  }
  
  /* Responsive: everything stacks naturally since image is on top */
  @media (max-width: 900px) {
    .origin-media img {
      max-width: 100%;
      max-height: 300px;
    }
  }
  </style>
  