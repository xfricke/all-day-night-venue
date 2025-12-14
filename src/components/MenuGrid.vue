<template>
    <div class="dropdown-wrapper">
    <div id="menu-section" class="grid">
      <article v-for="item in items" :key="item.name" class="menu-card card">
        <div class="meta">
          <h3>{{ item.name }}</h3>
          <p>{{ item.desc }}</p>
        </div>
      </article>
    </div>
  </div>
  </template>
  
  <script setup>
  const items = [
    { name:'Espresso', desc:'Nice acidity initally, sweetness of caramel and vanilla. Yummy long lasting flavours that linger afterwards.' },
    { name:'Cappuccino', desc:'Fluffy, smooth and great body. Chocolate on top just adds to the variety of texture and flavours.' },
    { name:'Hojicha', desc:'Warm, comforting and just super smooth overall.'}
  ]
  </script>
  
  <style scoped>

.dropdown-wrapper{
  background-color: rgba(92, 94, 58, 0.205);
  border-radius: 5px;
}

  .grid{
    display:grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap:18px;
    width: 50%;
    color: bisque;
  }
  .menu-card{ padding:10px; display:flex; gap:10px; align-items:center; transition: transform .2s ease; }
  .menu-card:hover{ transform: translateY(-2px); }

  .meta h3{ margin:0 0 6px; }
  .meta p{ margin:0; opacity:.85 }
  </style>
  