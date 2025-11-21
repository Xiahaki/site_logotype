<template>
  <aside class="filter-sidebar">
    <div class="filter-section">
      <div class="filter-header">Название категории</div>
      <div class="category-list">
        <div class="category-item">Название категории <span>3</span></div>
        <div class="category-item sub">Название категории <span>3</span></div>
        <div class="category-item sub">Название категории <span>3</span></div>
        <div class="category-item sub active">Название категории <span>3</span></div>
      </div>
    </div>
    <div class="filter-section">
      <div class="filter-title">Цена</div>
      <div class="price-inputs">
        <div class="price-input">
          <span class="label">от</span>
          <span class="value">5 500 ₽</span>
        </div>
        <div class="divider"></div>
        <div class="price-input">
          <span class="label">от</span>
          <span class="value">5 500 ₽</span>
        </div>
      </div>
    </div>
    <div class="filter-section">
      <div class="filter-header-with-clear">
        <div class="filter-title">Бренд</div>
        <button class="clear-button">Очистить</button>
      </div>
      <div class="search-input">
        <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg" opacity="0.3">
          <path fill-rule="evenodd" clip-rule="evenodd" d="M7.33333 2.75C4.80203 2.75 2.75 4.80203 2.75 7.33333C2.75 9.86464 4.80203 11.9167 7.33333 11.9167C9.86464 11.9167 11.9167 9.86464 11.9167 7.33333C11.9167 4.80203 9.86464 2.75 7.33333 2.75ZM1.25 7.33333C1.25 3.9736 3.9736 1.25 7.33333 1.25C10.6931 1.25 13.4167 3.9736 13.4167 7.33333C13.4167 10.6931 10.6931 13.4167 7.33333 13.4167C3.9736 13.4167 1.25 10.6931 1.25 7.33333Z" fill="#333333"/>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M10.5698 10.5696C10.8627 10.2768 11.3375 10.2768 11.6304 10.5696L14.5304 13.4696C14.8233 13.7625 14.8233 14.2374 14.5304 14.5303C14.2375 14.8232 13.7627 14.8232 13.4698 14.5303L10.5698 11.6303C10.2769 11.3374 10.2769 10.8625 10.5698 10.5696Z" fill="#333333"/>
        </svg>
        <input type="text" placeholder="Поиск" />
      </div>
      <div class="checkbox-list">
        <label class="checkbox-item checked">
          <input type="checkbox"></input>
          <span>Атрибут</span>
          <span class="count">3</span>
        </label>
        <label class="checkbox-item">
          <input type="checkbox"></input>
          <span>Атрибут</span>
          <span class="count">3</span>
        </label>
        <label class="checkbox-item">
          <input type="checkbox"></input>
          <span>Атрибут</span>
          <span class="count">3</span>
        </label>
        <label class="checkbox-item">
          <input type="checkbox"></input>
          <span>Атрибут</span>
          <span class="count">3</span>
        </label>
        <label class="checkbox-item">
          <input type="checkbox"></input>
          <span>Атрибут</span>
          <span class="count">3</span>
        </label>
        <label class="checkbox-item">
          <input type="checkbox"></input>
          <span>Атрибут</span>
          <span class="count">3</span>
        </label>
      </div>
      <div class="scrollbar"></div>
    </div>
    <div class="filter-section">
      <div class="filter-title">Размер</div>
      <div class="checkbox-list">
        <label class="checkbox-item">
          <input type="checkbox"></input>
          <span>Атрибут</span>
          <span class="count">3</span>
        </label>
        <label class="checkbox-item">
          <input type="checkbox"></input>
          <span>Атрибут</span>
          <span class="count">3</span>
        </label>
        <label class="checkbox-item">
          <input type="checkbox"></input>
          <span>Атрибут</span>
          <span class="count">3</span>
        </label>
        <label class="checkbox-item">
          <input type="checkbox"></input>
          <span>Атрибут</span>
          <span class="count">3</span>
        </label>
        <label class="checkbox-item">
          <input type="checkbox"></input>
          <span>Атрибут</span>
          <span class="count">3</span>
        </label>
        <label class="checkbox-item">
          <input type="checkbox"></input>
          <span>Атрибут</span>
          <span class="count">3</span>
        </label>
      </div>
    </div>
  </aside>
</template>
<script setup lang="ts">
</script>

<style scoped>
.filter-sidebar {
  width: 280px;
  display: flex;
  flex-direction: column;
  gap: 28px;
  background: var(--color-white);
}

.filter-section {
  display: flex;
  flex-direction: column;
  gap: 16px;
  position: relative;
}

.filter-header {
  display: flex;
  height: 30px;
  padding: 0 16px 0 8px;
  justify-content: space-between;
  align-items: center;
  font-size: 14px;
  font-weight: 400;
  line-height: 16px;
  color: var(--color-primary);
}

.filter-header span {
  color: var(--color-secondary);
  font-size: 12px;
  line-height: 14px;
}

.category-list {
  display: flex;
  flex-direction: column;
}

.category-item {
  display: flex;
  height: 30px;
  padding: 0 16px 0 8px;
  justify-content: space-between;
  align-items: center;
  font-size: 14px;
  font-weight: 400;
  line-height: 16px;
  color: var(--color-primary);
  cursor: pointer;
  transition: background 0.2s;
}

.category-item.sub {
  padding-left: 32px;
}

.category-item.active {
  background: var(--color-hover-bg);
  border-radius: 5px;
}

.category-item:hover {
  background: var(--color-hover-bg);
  border-radius: 5px;
}

.category-item span {
  color: var(--color-secondary);
  font-size: 12px;
  line-height: 14px;
}

.category-item.active span {
  color: var(--color-primary);
  opacity: 0.8;
}

.filter-title {
  font-size: 16px;
  font-weight: 700;
  line-height: 20px;
  color: var(--color-primary);
}

.filter-header-with-clear {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
}

.clear-button {
  font-size: 12px;
  font-weight: 400;
  line-height: 12px;
  color: var(--color-secondary);
  text-decoration: underline;
  cursor: pointer;
  transition: color 0.2s;
}

.clear-button:hover {
  color: var(--color-primary);
}

.price-inputs {
  display: flex;
  align-items: center;
  gap: 16px;
}

.price-input {
  display: flex;
  padding: 10px 8px;
  align-items: center;
  gap: 6px;
  flex: 1;
  border-radius: 4px;
  border: 1px solid var(--color-border);
  background: var(--color-white);
}

.price-input .label {
  font-size: 12px;
  font-weight: 400;
  line-height: 14px;
  color: var(--color-secondary);
}

.price-input .value {
  font-size: 14px;
  font-weight: 400;
  line-height: 16px;
  color: var(--color-primary);
}

.divider {
  width: 10px;
  height: 1px;
  background: var(--color-border);
}

.search-input {
  display: flex;
  padding: 10px 12px;
  align-items: flex-start;
  gap: 8px;
  border-radius: 4px;
  border: 1px solid var(--color-border);
  background: var(--color-white);
}

.search-input input {
  flex: 1;
  border: none;
  outline: none;
  font-size: 14px;
  font-weight: 400;
  line-height: 16px;
  color: var(--color-primary);
}

.search-input input::placeholder {
  color: var(--color-secondary);
}

.checkbox-list {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.checkbox-item {
  display: flex;
  height: 20px;
  padding-right: 16px;
  align-items: center;
  gap: 12px;
  cursor: pointer;
}

.checkbox {
  width: 20px;
  height: 20px;
  border-radius: 3px;
  border: 1px solid var(--color-border);
  flex-shrink: 0;
  position: relative;
  background: var(--color-white);
}

.checkbox.checked {
  background: var(--color-brand-primary);
  border-color: var(--color-brand-primary);
}

.checkbox.checked::after {
  content: '';
  position: absolute;
  left: 6px;
  top: 2px;
  width: 5px;
  height: 10px;
  border: solid white;
  border-width: 0 2px 2px 0;
  transform: rotate(45deg);
}

.checkbox-item span {
  font-size: 14px;
  font-weight: 400;
  line-height: 16px;
  color: var(--color-primary);
  flex: 1;
}

.checkbox-item .count {
  font-size: 12px;
  font-weight: 400;
  line-height: 14px;
  color: var(--color-secondary);
  flex: 0;
}

.scrollbar {
  width: 3px;
  height: 121px;
  position: absolute;
  right: 0;
  bottom: -59px;
  border-radius: 10px;
  background: var(--color-icons);
}

@media (max-width: 1024px) {
  .filter-sidebar {
    width: 240px;
  }
}

@media (max-width: 768px) {
  .filter-sidebar {
    display: none;
  }
}
</style>
