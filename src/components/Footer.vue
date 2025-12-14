<template>
    <footer class="footer">
      <div class="container footer-inner">
  
        <p class="design-credit">Designed by Felix Dundon</p>
  
        <p class="footer-item">
          124 Wellington Parade, East Melbourne VIC 3002
        </p>
  
        <p class="design-credit">Make a booking!</p>
        <p class="footer-item">
          <a href="#0457 526 194">0457 526 195</a>
        </p>
  
      </div>
    </footer>
  </template>
  
  <style scoped>
  .footer {
    padding: 40px 0;
    margin-top: 60px;
    border-top: 1px solid rgba(255,255,255,0.08);
    background: rgba(0,0,0,0.1);
    backdrop-filter: blur(4px);
    color: bisque;
  }

  
  .footer-inner {
    text-align: center;
    display: flex;
    flex-direction: column;
    gap: 10px;
    color: var(--cream);
  }
  
  /* “Designed by Felix” gets soft emphasis */
  .design-credit {
    font-size: 0.95rem;
    margin: 0;
    letter-spacing: 0.5px;
  }
  
  /* Address + phone styling */
  .footer-item a{
    margin: 0;
    opacity: 0.9;
    font-size: 1rem;
    letter-spacing: 0.3px;
    text-decoration: none;
    color: bisque;
  }
  
  .footer-item a:active{
    margin: 0;
    opacity: 0.9;
    font-size: 1rem;
    letter-spacing: 0.3px;
    text-decoration: none;
    color: rgb(167, 138, 104);
  }

  /* Mobile stays identical — no change needed, but you can add spacing if desired */
  @media (max-width: 600px) {
    .footer {
      padding: 32px 0;
    }
  }
  </style>
  