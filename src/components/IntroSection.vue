<template>
    <section class="section intro">
      <div class="container intro-grid">
        <div class="intro-copy">
          <h2>Intriguing, Social and Cozy</h2>
          <p>
            Make yourself at home with our all new record cafe/bar. This is both a day and night venue
          </p>
          <p>
            Set the mood, browse the menu, and stay as long as you like.
            Your table's always here.
          </p>
          <h3>See below for our socials!</h3>
          <p>
           @felixdundon
           @Hazthi
           @Daviscallum
          </p>
        </div>
  
        <!-- Image (left on desktop, second on mobile) -->
        <figure class="intro-media">
          <img
            src="@/assets/record.jpg"
            loading="lazy"
          />
        </figure>
      </div>
    </section>
  </template>
  
  
  <style scoped>
  /* Layout */
  .intro-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding: 20px;
  }
  
  /* Image */
  .intro-media {
    border-radius: 16px;
    overflow: hidden;
    border: 1px solid rgba(255,255,255,0.08);
    background: rgba(255,255,255,0.03);
    
  }
  
  .intro-media img {
    display: block;
    width: 100%;
    height: 100%;
    object-fit: cover;           
    filter: brightness(0.95);
  }
  
  .intro-copy{
    background-color: rgba(92, 94, 58, 0.205);
    border-radius: 16px;
    padding: 20px;
    backdrop-filter: blur(0px); /* Adjust the blur intensity as needed */
    border-style: solid;
    border-color: rgba(0, 0, 0, 0.635);
    color: bisque;
  }

  .intro-copy h2 {
    margin: 0 0 10px;
    font-size: clamp(28px, 4vw, 42px);
  }
  .intro-copy p {
    margin: 0 0 12px;
    opacity: 0.9;
  }
 
  
  /* Mobile: stack with TEXT first, IMAGE second */
  @media (max-width: 900px) {
    .intro-grid {
      grid-template-columns: 1fr;
    }
    .intro-copy { order: -1; }   /* put text above image on mobile */
  }
  </style>
  