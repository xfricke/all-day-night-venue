<template>
    <section class="landing-banner">
      <img src="@/assets/landing.jpg" alt="Coffee banner" class="banner-image" />
      <div class="banner-overlay">
        <h1 class="banner-text">Welcome</h1>
        <p class="banner-subtext">A warm cup, a quiet moment, a creative space.</p>
      </div>
    </section>
  </template>

<style scoped>

.landing-banner {
  position: relative;
  width: 100%;
  height: 70vh; 
  overflow: hidden;
  color: aliceblue;
}

.banner-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  filter: brightness(0.75); /* slight dim for text contrast */
}

.banner-overlay {
  position: absolute;
  top: 55%; /* slightly lower than vertical center */
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  color: var(--cream);
  text-shadow: 0 2px 10px rgba(0,0,0,0.4);
}

.banner-text {
  font-size: clamp(2.5rem, 5vw, 5rem);
  margin: 0;
  letter-spacing: 1px;
}

.banner-subtext {
  font-size: 1.2rem;
  margin-top: 12px;
  opacity: 0.9;
}
</style>