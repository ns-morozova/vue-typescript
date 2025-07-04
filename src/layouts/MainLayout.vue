<template>
    <div class="layout">
      <header class="header">
        <!-- Тут можно разместить меню -->
        <h2>Header</h2>
      </header>
      <main>
        <slot />
      </main>
      <footer class="footer">
        <p>&copy; 2025 Все права защищены</p>
      </footer>
    </div>
  </template>
  
  <style scoped>
  .layout {
    width: 100%;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
  }
  
  .header,
  .footer {
    background-color: #f3f4f6;
    text-align: center;
  }
  
  .footer {
    margin-top: auto;
  }
  </style>