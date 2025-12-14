<script setup lang="ts">
type Location = { name: string; desc?: string }
const locations: Location[] = [
  { name: "South Melbourne",
    desc: "Excellent proximity to the city"
  },
]
</script>

<template>
  <div class="dropdown-wrapper">
  <div id="location-section" class="grid">
    <article v-for="l in locations" :key="l.name" class="location-card">
      <div class="meta">
        <h4>{{ l.name }}</h4>
        <h4>{{ l.desc }}</h4>
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

.grid{
    display:grid;
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
    color: bisque;
}
.location-card{ padding:10px; display:flex; gap:10px; align-items:center; transition: transform .2s ease; }
.location-card:hover{ transform: translateY(-2px); }
</style>
