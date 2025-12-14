<template>
    <section class="section collab">
      <div class="container collab-grid card">
        <!-- Brand / Visual -->
        <figure class="collab-media" v-if="banner">
          <img :src="banner" alt="OutOfOffice collaboration banner" loading="lazy" />
        </figure>
        <div class="collab-media placeholder" v-else>
          <div class="badge">OutOfOffice</div>
        </div>
  
        <!-- Copy -->
        <div class="collab-copy">
          <p class="eyebrow">Evenings</p>
          <h2>In collaboration with <span class="brand">OutOfOffice</span> Dance Club</h2>
          <p class="lede">
            By day, lounge and relax with a warm or iced cup of coffee . By night, entrench yourself into some carefully curated rhythms and warm lights.
            We've teamed up with OutOfOffice to host intimate and unforgettable evenings.
          </p>
  
          <ul class="highlights">
            <li>Vinyl-friendly setup & tuned room acoustics</li>
            <li>Small-format dance floor with seated lounge</li>
            <li>Warm lighting, minimal phones, maximum vibe</li>
          </ul>
  
          <div class="details">
            <div class="row">
              <span class="label">When</span>
              <span class="value">{{ when }}</span>
            </div>
            <div class="row" v-if="where">
              <span class="label">Where</span>
              <span class="value">{{ where }}</span>
            </div>
          </div>
  
        </div>
      </div>
  
    

      <div class="row">
        <figure class="media">
          <img src="@/assets/ooo1.jpg" alt="" />
        </figure>
        <div class="copy">
          <h3>Evening Sessions</h3>
          <p>
            Settle into our evening sessions starting from 7pm.
          </p>
        </div>
      </div>

      <!-- ROW 2 -->
      <div class="row reverse">
        <figure class="media">
          <img src="@/assets/ooo2.jpg" alt="" />
        </figure>
        <div class="copy">
          <h3>Curated Atmosphere</h3>
          <p>
            Always a lively, fun and social environment
        </p>
        </div>
      </div>

      <!-- ROW 3 -->
      <div class="row">
        <figure class="media">
          <img src="@/assets/ooo3.jpg" alt="" />
        </figure>
        <div class="copy">
          <h3>Gateway for Opportunity</h3>
          <p>
           Provides a space to network with new individuals
          </p>
        </div>
      </div>
        <!-- Optional ticker -->
        <div class="marquee" v-if="showTicker">
                <div class="track">
                <span v-for="i in 10" :key="i">
                    ✦ OutOfOffice X Café — Evenings · Enquire with us to play here ·
                </span>
                </div>
            </div>

    </section>
  </template>
  
  <script setup lang="ts">

  import oooLogo from '@/assets/ooobrand.jpg'

  interface Props {
    when?: string
    where?: string
    banner?: string 
    learnMoreHref?: string
    showTicker?: boolean
  }
  withDefaults(defineProps<Props>(), {
    when: 'Selected Saturdays · 6:30 - 11:30 PM',
    where: 'Café, Melbourne',
    banner: oooLogo,
    learnMoreHref: '',
    showTicker: true
  })
  </script>
  
  <style scoped>

 /* The card container */
 .collab-grid {
  margin-top: 50px;  
  max-width: 1200px;      /* hard limit */
  margin-inline: auto;    /* centers the whole grid */
  width: 100%;
  display: grid;
  grid-template-columns: minmax(280px, 520px) 1fr;
  align-items: center;
  gap: 32px;
  color: bisque;
  margin-bottom: 50px;
}



.collab-copy {
  text-align: center;            
  margin-inline: auto;           
  max-width: 62ch;     
}

.collab-media {
  justify-self: center;
  width: 100%;
  max-width: 520px;
  aspect-ratio: 4 / 3;
  border-radius: 14px;
  overflow: hidden;
  border: 1px solid rgba(255,255,255,0.08);
}


/* Image fills the box without stretching */
.collab-media img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.highlights{
    list-style: none;
}

/* Placeholder block matches sizing */
.collab-media.placeholder {
  display: grid;
  place-items: center;
}

/* Little brand badge example */
.badge {
  padding: 8px 12px;
  border-radius: 999px;
  border: 1px solid rgba(255,255,255,0.12);
  background: rgba(255,255,255,0.05);
  font-weight: 600;
  letter-spacing: .4px;
}

/* Mobile: stack columns */
@media (max-width: 900px) {
  .collab-grid {
    grid-template-columns: 1fr;
    gap: 18px;
  }

  .collab-copy{
    padding: 10px;          

  }
}

  .eyebrow{
    margin:0 0 6px; opacity:.85; letter-spacing:.6px; text-transform:uppercase; font-size:.9rem;
  }
  h2{
    margin:0 0 10px; font-size: clamp(28px, 4vw, 42px);
  }
  .brand{ color: var(--accent); }

  .lede{ opacity:.92; margin:0 0 14px; max-width: 60ch; }
  
  .highlights{
    margin: 0 0 14px; padding-left: 18px;
    opacity: .92;
  }
  
  .highlights li{ margin: 6px 0; }
  
  .details{
    margin: 10px 0 14px;
    border-top: 1px solid rgba(255,255,255,0.08);
    border-bottom: 1px solid rgba(255,255,255,0.08);
    padding: 10px 0;
    color: bisque;
  }
  .details .row{
    display:flex; gap: 10px; align-items: baseline;
  }
  .details .label{
    width: 64px; opacity: .7; font-size: .95rem;
  }
  .details .value{
    opacity: .95;
  }
  
  .cta-row{
    display:flex; gap:12px; align-items:center; flex-wrap: wrap;
  }

  .text-link{
    color: var(--accent); text-decoration: none;
  }
  .text-link:hover{ text-decoration: underline; }

  .row {
  color: bisque;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2px;
  align-items: center;
  margin-bottom: 28px;
}

/* Reverse order row (Image right / Text left) */
.row.reverse {
  direction: rtl; /* invert layout without changing markup */
}
.row.reverse > * {
  direction: ltr; /* reset text direction back to normal */
}

/* Media (images) */
.media {
  margin: 0;
  border-radius: 16px;
  overflow: hidden;
  border: 1px solid rgba(255,255,255,0.1);
  background: rgba(255,255,255,0.04);
}

.media img {
  width: 100%;
  height: auto;
  object-fit: cover;
  display: block;
  aspect-ratio: 5 / 3; 
}

.copy{
    text-align: center;            
    max-width: 60ch;
    margin: 0 auto;     
}

.copy h3 {
  margin: 0 0 10px;
  font-size: clamp(24px, 4vw, 36px);
}
.copy p {
  margin: 0;
  opacity: 0.9;
  font-size: 23px;
  
}

/* Mobile responsiveness */
@media (max-width: 900px) {
  .row {
    grid-template-columns: 1fr;
    text-align: center;
  }

  .copy { order: -1; padding: 50px; }

  /* Don’t reverse on mobile */
  .row.reverse {
    direction: ltr;
  }

  .media img {
    aspect-ratio: 5 / 3; /* keeps layout stable */

  }
}
  
  /* Ticker */
  .marquee{
    margin-top: 16px;
    border-top: 1px solid rgba(255,255,255,0.08);
    border-bottom: 1px solid rgba(255,255,255,0.08);
    overflow: hidden;
    mask-image: linear-gradient(90deg, transparent, #000 12%, #000 88%, transparent);
    -webkit-mask-image: linear-gradient(90deg, transparent, #000 12%, #000 88%, transparent);
  }
  .track{
    display:inline-block; white-space:nowrap; will-change:transform;
    padding: 10px 0; animation: marquee 20s linear infinite; color: bisque;
  }
  .track span{ padding-right: 28px; text-transform: uppercase; opacity: .9; }
  
  @keyframes marquee{
    from{ transform: translateX(0); }
    to{ transform: translateX(-50%); }
  }
  
  /* Responsive */
  @media (max-width: 980px){
    .collab-grid{ grid-template-columns: 1fr; }
    .collab-media{ order: 2; }  /* image second */
    .collab-copy{ order: -1; }  /* text first on mobile */
  }
  </style>
  