<template>
  <header class="app-header">
    <div class="logo-section">
      <div class="logo-button">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M5 21C4.45 21 3.979 20.8043 3.587 20.413C3.19567 20.021 3 19.55 3 19V5C3 4.45 3.19567 3.979 3.587 3.587C3.979 3.19567 4.45 3 5 3H19C19.55 3 20.021 3.19567 20.413 3.587C20.8043 3.979 21 4.45 21 5V19C21 19.55 20.8043 20.021 20.413 20.413C20.021 20.8043 19.55 21 19 21H5ZM6 17H18L14.25 12L11.25 16L9 13L6 17Z" fill="#73AFF4"/>
        </svg>
        <span>Логотип</span>
      </div>
      <button class="catalog-button">Каталог</button>
    </div>
    <div class="search-box">
      <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M15.5 14H14.71L14.43 13.73C15.41 12.59 16 11.11 16 9.5C16 5.91 13.09 3 9.5 3C5.91 3 3 5.91 3 9.5C3 13.09 5.91 16 9.5 16C11.11 16 12.59 15.41 13.73 14.43L14 14.71V15.5L19 20.49L20.49 19L15.5 14ZM9.5 14C7.01 14 5 11.99 5 9.5C5 7.01 7.01 5 9.5 5C11.99 5 14 7.01 14 9.5C14 11.99 11.99 14 9.5 14Z" fill="#5A5A5A"/>
      </svg>
      <input type="text" placeholder="Поиск по 100 000 товаров" />
    </div>
    <nav class="nav-links">
      <a href="#">Информация о компании</a>
      <a href="#">Контакты</a>
      <a href="#">Полезные ссылки</a>
    </nav>
  </header>
</template>
<script setup lang="ts">
</script>
<style scoped>

.app-header {
  display: flex;
  align-items: center;
  gap: 24px;
  padding: 12px 128px;
  background: var(--color-white);
  width: 100%;
}

.logo-section {
  display: flex;
  align-items: flex-start;
  gap: 8px;
}

.logo-button {
  display: flex;
  height: 48px;
  padding: 0 24px;
  align-items: center;
  gap: 8px;
  font-family: 'Inter', -apple-system, Roboto, Helvetica, sans-serif;
  font-size: 16px;
  font-weight: 400;
  color: #000;
}

.catalog-button {
  display: flex;
  height: 48px;
  padding: 8px 24px;
  align-items: center;
  gap: 10px;
  border-radius: 8px;
  border: 1px solid var(--color-brand-primary);
  font-family: 'Inter', -apple-system, Roboto, Helvetica, sans-serif;
  font-size: 14px;
  font-weight: 500;
  color: #000;
  background: var(--color-white);
  transition: background 0.2s;
}

.catalog-button:hover {
  background: var(--color-hover-bg);
}

.search-box {
  display: flex;
  padding: 4px 16px;
  align-items: center;
  gap: 8px;
  flex: 1;
  border-radius: 10px;
  border: 1px solid var(--color-brand-primary);
  background: var(--color-white);
}

.search-box input {
  flex: 1;
  border: none;
  outline: none;
  font-size: 16px;
  color: #5a5a5a;
  line-height: 150%;
}

.search-box input::placeholder {
  color: #5a5a5a;
}

.nav-links {
  display: flex;
  align-items: flex-start;
  gap: 20px;
}

.nav-links a {
  font-size: 14px;
  font-weight: 400;
  color: #393939;
  text-decoration: none;
  white-space: nowrap;
  transition: color 0.2s;
}

.nav-links a:hover {
  color: var(--color-hover-text);
}

@media (max-width: 1200px) {
  .app-header {
    padding: 12px 40px;
    flex-wrap: wrap;
  }
  
  .search-box {
    order: 3;
    width: 100%;
  }
}

@media (max-width: 768px) {
  .app-header {
    padding: 12px 20px;
  }
  
  .nav-links {
    display: none;
  }
}
</style>
