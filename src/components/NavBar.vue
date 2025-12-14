<template>
    <nav class="navbar">
      <div class="navbar-container">
        <div class="navbar-logo">
            Café
        </div>
  
        <ul class="navbar-links">
        </ul>
      </div>
    </nav>
  </template>
  
  <script setup>
  import { RouterLink } from 'vue-router'
  </script>
  
  <style scoped>
  .navbar {
    top: 0;
    width: 100%;
    z-index: 1000;
    background: rgba(31, 22, 18, 0.85);
    backdrop-filter: blur(6px);
    box-shadow: 0 1px 12px rgba(0, 0, 0, 0.3);
    transition: background 0.3s ease, box-shadow 0.3s ease;
  }
  
  .navbar-container {
    margin: 0 auto;
    padding: 18px 32px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  
  .navbar-logo {
    font-family: "Playfair Display", serif;
    font-size: 1.6rem;
    letter-spacing: 1px;
    color: bisque;
    cursor: pointer;
    user-select: none;
    transition: opacity 0.3s ease;
  }
  .navbar-logo:hover {
    opacity: 0.8;
  }
  
  .navbar-links {
    list-style: none;
    display: flex;
    gap: 36px;
    margin: 0;
    padding: 0;
  }
  
  .nav-link {
    text-decoration: none;
    color: var(--cream);
    font-size: 1.1rem;
    letter-spacing: 0.5px;
    position: relative;
    transition: color 0.3s ease;
    color: bisque;
  }
  
  .nav-link:hover {
    color: rgb(174, 165, 155);
  }
  
  </style>
  