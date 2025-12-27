<template>
    <section class="section origin" :style="bgStyle" style="margin-top: 100px; margin-bottom: 20px;">
      <div class="container origin-wrap card">
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

          <div class="seedsLogo">
            <img src="@/assets/sevenseeds.png"></img>
        </div>

        </div>
    
       
      </div>
    </section>
  </template>
  
  <script setup>
 import bg from '@/assets/coffee.JPG'
const bgStyle = {
  backgroundImage: `url(${bg})`,
}
  </script>
  
  <style scoped>
 .origin {
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;

  display: flex;
  align-items: center;      /* vertical center */
  justify-content: center;  /* horizontal center */
  padding: 4rem 1.5rem;     /* mobile breathing room */
}

.origin-wrap {
  max-width: 800px;
  width: 100%;              /* allows shrink on mobile */
  border-radius: 16px;
  color: bisque;
text-align: center;
}


  
  
  /* Text styling */
  .eyebrow {
    text-transform: uppercase;
    opacity: 0.7;
    letter-spacing: 2px;
    margin: 0 0 8px;
    font-size: 0.85rem;
  }
  
  .origin-copy{
    max-width: 1200px;
    background-color: rgb(45, 43, 32);
    padding: 30px 20px;
    border-radius: 5px;
    border-style: solid;
    border-color: bisque;
  }

  @media (max-width: 1200px) {
    .origin-wrap {
        padding: 52px 150px;
    }
    
  }

  @media (max-width: 700px) {
    .origin-wrap {
        padding: 52px 50px;
    }
  }

  @media (max-width: 400px){
    .seedsLogo img{
        width: 100px;
        height: 100px;
    }
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
  
  </style>
  