<script setup lang="ts">

import stkilda from '@/assets/stkildard.jpg'

type Location = { name: string; desc?: string; img?: string; }
const locations: Location[] = [
  { name: "St Kilda Road",
    desc: "Excellent proximity to the city. Lush and leafy road with a successful corporate setting. Great feel of community, peaceful vibes and friendly faces.",
    img: stkilda
  },
]
</script>

<template>
  <div class="dropdown-wrapper">
  <div id="location-section" class="grid">
    <article v-for="l in locations" :key="l.name" class="location-card">
      <div class="meta">
        <h3>{{ l.name }}</h3>
        <p>{{ l.desc }}</p>
        <div class="location-photo">
          <img :src="stkilda" />
        </div>
      </div>
    </article>
  </div>
  </div>
</template>

<style scoped>

.dropdown-wrapper{
  background-color: rgba(92, 94, 58, 0.205);
  border-radius: 5px;
}

.location-photo{
  display: flex;
  align-items: center;      /* vertical center */
  justify-content: center;
}

.location-photo img{
  width: 200px;
  height: 150px;
  border-style: solid;
  border-width: 2px;
  border-radius: 5px;
}

.grid{
    display:grid;
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
    color: bisque;
    

}
.location-card{ padding:10px; display:flex; gap:10px; align-items:center; }

.meta h3{ margin:0 0 6px; }
.meta p{ margin:0; opacity:.85 }
</style>
