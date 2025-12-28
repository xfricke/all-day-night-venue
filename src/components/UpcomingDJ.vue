<template>
  <p class="eyebrow" style="margin-top: 50px;">Lineup</p>
    <!-- Header -->
    <header class="DJ-header">
          <h2>Take a look at our upcoming DJs</h2>
          <p class="lede">
            An expansive rotation of your favourite DJs. These people will keep the night alive and the vibrations maximum
          </p>
        </header>
    <section class="section upcoming">
      
      <div class="dj-grid">
        <div
          v-for="(dj, index) in props.djs"
          :key="index"
          class="container card dj-wrap"
        >
          <!-- Profile image -->
          <figure class="dj-photo">
            <img :src="dj.photo" :alt="`Profile photo of ${dj.name}`" loading="lazy" />
          </figure>

          <!-- Copy -->
          <div class="dj-copy">
            <h3 class="dj-name">{{ dj.name }}</h3>
            <p class="dj-meta">{{ dj.meta }}</p>
            <p class="dj-desc">{{ dj.desc }}</p>
          </div>
        </div>
      </div>
              
    
    
      
  
      <!-- Marquee -->
      <div class="marquee" aria-label="Scrolling announcements">
        <div class="track">
          <span v-for="(dj, index) in props.djs" :key="'a' + index">
            🎧 Upcoming DJ · {{ dj.name }} · {{ dj.meta }} · Enquire with us to play here! ·
          </span>
        </div>

        <div class="track">
          <span v-for="(dj, index) in props.djs" :key="'b' + index">
            🎧 Upcoming DJ · {{ dj.name }} · {{ dj.meta }} · Enquire with us to play here! ·
          </span>
        </div>
      </div>
    </section>
  </template>
  
  <script setup lang="ts">

    import hasthiPhoto from '@/assets/oew6 17.6.jpg'
    import maxyPhoto from '@/assets/maxy.jpg'

    interface DJ {
  name: string
  meta: string
  desc: string
  photo: string
}
const props = withDefaults(defineProps<{ djs?: DJ[] }>(), {
  djs: () => [
    {
      name: 'Hasthika',
      meta: 'Saturday · 9:00 PM · Vinyl Only',
      desc: 'Smooth and lustful R&B played by yours truly, Hasthika.',
      photo: hasthiPhoto,
    },
    {
      name: 'Maxy',
      meta: 'Friday · 8:00 PM · Deep House',
      desc: 'Warm grooves and late-night rhythms to set the tone. ',
      photo: maxyPhoto, 
    }
  ]
})
  
  </script>
  
  <style scoped>
  
  /* Card layout */
  /* Parent layout */
.dj-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  justify-content: center;
}

/* Card */
.dj-wrap {
  display: grid;
  grid-template-columns: 160px 1fr;
  gap: 20px;
  align-items: center;
  padding: 18px;
  border-radius: 16px;
  width: 100%;
  max-width: 520px; /* controls size */
  margin: 0 auto;
}

/* Responsive stacking */
@media (max-width: 900px) {
  .dj-grid {
    grid-template-columns: 1fr;
  }
}


  .DJ-header {
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
  
  .marquee {
  display: flex;
  overflow: hidden;
  position: relative;
  border-top: 1px solid rgba(255,255,255,0.08);
  border-bottom: 1px solid rgba(255,255,255,0.08);
  mask-image: linear-gradient(90deg, transparent, #000 12%, #000 88%, transparent);
  -webkit-mask-image: linear-gradient(90deg, transparent, #000 12%, #000 88%, transparent);
  color: bisque;
}

.track {
  display: flex;
  white-space: nowrap;
  animation: marquee 38s linear infinite;
  padding: 10px 0;
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

/* Keyframes */
@keyframes marquee {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-100%);
  }
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
  