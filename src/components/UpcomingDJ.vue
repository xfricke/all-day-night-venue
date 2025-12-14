<template>
    <section class="section upcoming">
      <div class="container card dj-wrap">
        <!-- Profile image -->
        <figure class="dj-photo">
            <img :src="hasthiPhoto" /> :alt="`Profile photo of ${name}`" loading="lazy" />
        </figure>
  
        
        <div class="dj-copy">
          <h3 class="dj-name">{{ name }}</h3>
          <p class="dj-meta">{{ meta }}</p>
          <p class="dj-desc">{{ desc }}</p>
          <p class="dj-socials">{{ socials }}</p>
        </div>
      </div>
  
      <!-- Marquee -->
      <div class="marquee" aria-label="Scrolling announcements">
        <div class="track">
          <span v-for="i in 8" :key="i">
            🎧 Upcoming DJ · {{ name }} · {{ meta }} · Enquire with us to play here! ·
          </span>
        </div>
      </div>
    </section>
  </template>
  
  <script setup lang="ts">

    import hasthiPhoto from '@/assets/oew6 17.6.jpg'


  interface Props {
    name?: string
    meta?: string     
    desc?: string
    photo?: string
  }
  const props = withDefaults(defineProps<Props>(), {
    name: 'Hasthika',
    meta: 'Saturday · 9:00 PM · Vinyl Only',
    desc:
      'Smooth and lustful R&B played by yours truly, Hasthika. ',
    photo: hasthiPhoto,
  })
  
  const { name, meta, desc, photo } = props
  </script>
  
  <style scoped>
  .upcoming { padding-top: 48px; }
  
  /* Card layout */
  .dj-wrap {
    display: grid;
    grid-template-columns: 160px 1fr;
    gap: 20px;
    align-items: center;
    padding: 18px;
    border-radius: 16px;
  }
  
  /* profile photo */
  .dj-photo {
    margin: 0;
    width: 160px; height: 160px;
    border-radius: 50%;
    overflow: hidden;
    border: 1px solid rgba(255,255,255,0.12);
    box-shadow: 0 8px 24px rgba(0,0,0,0.25);
    background: rgba(255,255,255,0.04);
  }
  .dj-photo img {
    width: 100%; height: 100%; object-fit: cover;
  }
  
  /* DJ info */
  .dj-copy .dj-name {
    margin: 0 0 6px;
    font-size: clamp(22px, 3.2vw, 30px);
    color: bisque;
  }
  .dj-copy .dj-meta {
    margin: 0 0 8px;
    opacity: 0.85;
    color: bisque;
  }
  .dj-copy .dj-desc {
    margin: 0 0 12px;
    max-width: 60ch;
    opacity: 0.9;
    color: bisque;
  }

  .dj-copy .dj-socials{
    margin: 0 0 12px;
    max-width: 60ch;
    opacity: 0.9;
    color: bisque;
  }
  
  /* scroll */
  .marquee {
    margin-top: 16px;
    border-top: 1px solid rgba(255,255,255,0.08);
    border-bottom: 1px solid rgba(255,255,255,0.08);
    overflow: hidden;
    mask-image: linear-gradient(90deg, transparent, #000 12%, #000 88%, transparent);
    -webkit-mask-image: linear-gradient(90deg, transparent, #000 12%, #000 88%, transparent);
    color: bisque;
  }
  .track {
    display: inline-block;
    white-space: nowrap;
    will-change: transform;
    padding: 10px 0;
    animation: marquee 18s linear infinite;
  }
  .track span {
    display: inline-block;
    padding-right: 28px;
    letter-spacing: .5px;
    color: var(--cream);
    opacity: .9;
    text-transform: uppercase;
    font-size: 0.95rem;
  }
  
  @keyframes marquee {
    from { transform: translateX(0); }
    to   { transform: translateX(-50%); } /* repeats since we dup content via v-for */
  }
  
  /* Responsive */
  @media (max-width: 900px) {
    .dj-wrap {
      grid-template-columns: 1fr;
      text-align: center;
    }
    .dj-photo {
      justify-self: center;
    }
    .dj-copy .dj-desc { margin-left: auto; margin-right: auto; }
  }
  </style>
  