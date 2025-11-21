<template>
  <div class="product-card" :class="{ 'unavailable': !available }">
    <div class="product-image">
      <svg class="placeholder-icon" width="60" height="60" viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
        <g opacity="0.5">
          <path fill-rule="evenodd" clip-rule="evenodd" d="M58.23 11.1487C58.7521 11.3571 59.1997 11.7171 59.5152 12.1823C59.8307 12.6476 59.9996 13.1966 60 13.7587V46.2412C59.9996 46.8034 59.8307 47.3524 59.5152 47.8177C59.1997 48.2829 58.7521 48.6429 58.23 48.8512L31.0425 59.7262C30.3721 59.9944 29.6242 59.9944 28.9538 59.7262L1.76625 48.8512C1.24488 48.6423 0.79802 48.282 0.483227 47.8169C0.168434 47.3517 0.000130725 46.8029 0 46.2412L0 13.7587C0.000130725 13.1971 0.168434 12.6483 0.483227 12.1831C0.79802 11.718 1.24488 11.3577 1.76625 11.1487L27.9113 0.689995L27.9488 0.678745L28.9538 0.273745C29.6253 0.00461759 30.3747 0.00461759 31.0463 0.273745L32.055 0.678745L32.0925 0.689995L58.23 11.1487ZM39.015 7.5L15.9375 16.7287L6.9225 13.125L3.75 14.3962V15.8962L28.125 25.6462V55.3537L30 56.1037L31.875 55.3537V25.65L56.25 15.9V14.4L53.0775 13.1287L30 22.3537L20.985 18.75L44.0625 9.52125L39.015 7.5Z" fill="#A6A9C7"/>
        </g>
      </svg>
      <div class="badge-top">
        <div class="hot-badge">
          <span>Хит продаж</span>
          <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M3.33331 11.6667C3.33331 10.2083 3.68054 8.90972 4.37498 7.77083C5.06942 6.63194 5.83331 5.67361 6.66665 4.89583C7.49998 4.11806 8.26387 3.52417 8.95831 3.11417L9.99998 2.5V5.25C9.99998 5.76389 10.1736 6.17 10.5208 6.46833C10.868 6.76667 11.2569 6.91611 11.6875 6.91667C11.9236 6.91667 12.1494 6.86806 12.365 6.77083C12.5805 6.67361 12.7783 6.51389 12.9583 6.29167L13.3333 5.83333C14.3333 6.41667 15.1389 7.22555 15.75 8.26C16.3611 9.29444 16.6666 10.43 16.6666 11.6667C16.6666 12.8889 16.368 14.0036 15.7708 15.0108C15.1736 16.0181 14.3889 16.8128 13.4166 17.395C13.6528 17.0617 13.8369 16.6969 13.9691 16.3008C14.1014 15.9047 14.1672 15.485 14.1666 15.0417C14.1666 14.4861 14.0625 13.9617 13.8541 13.4683C13.6458 12.975 13.3472 12.5342 12.9583 12.1458L9.99998 9.25L7.06248 12.1458C6.6597 12.5486 6.35415 12.9931 6.14581 13.4792C5.93748 13.9653 5.83331 14.4861 5.83331 15.0417C5.83331 15.4861 5.89942 15.9064 6.03165 16.3025C6.16387 16.6986 6.34776 17.0631 6.58331 17.3958C5.61109 16.8125 4.82637 16.0172 4.22915 15.01C3.63192 14.0028 3.33331 12.8883 3.33331 11.6667ZM9.99998 11.5833L11.7708 13.3125C12.0069 13.5486 12.1875 13.8125 12.3125 14.1042C12.4375 14.3958 12.5 14.7083 12.5 15.0417C12.5 15.7222 12.2569 16.3019 11.7708 16.7808C11.2847 17.2597 10.6944 17.4994 9.99998 17.5C9.30554 17.5 8.71526 17.2603 8.22915 16.7808C7.74304 16.3014 7.49998 15.7217 7.49998 15.0417C7.49998 14.7222 7.56248 14.4131 7.68748 14.1142C7.81248 13.8153 7.99304 13.5481 8.22915 13.3125L9.99998 11.5833Z" fill="#FF8743"/>
          </svg>
        </div>
      </div>
      <div v-if="discount" class="discount-badge">{{ discount }}%</div>
    </div>
    <div class="product-info">
      <div class="product-brand">{{ brand }}</div>
      <div class="product-name" :class="{ 'hovered': isHovered }">{{ name }}</div>
    </div>
    <div v-if="available" class="product-price">
      <span class="current-price">{{ currentPrice }} ₽</span>
      <span v-if="originalPrice" class="original-price">{{ originalPrice }} ₽</span>
    </div>
    <button class="buy-button" :class="{ 'unavailable': !available }">
      {{ available ? 'Купить' : 'Сообщить о поступлении' }}
    </button>
  </div>
</template>
<script setup lang="ts">
import { ref } from 'vue'
interface Props {
  brand?: string
  name?: string
  currentPrice?: string
  originalPrice?: string
  discount?: number
  available?: boolean
}

withDefaults(defineProps<Props>(), {
  brand: 'Бренд',
  name: 'Полное название товара в несколько строк для вида с обрывом в конце...',
  currentPrice: '5 990',
  originalPrice: '5 990',
  discount: 25,
  available: true
})

const isHovered = ref(false)
</script>
<style scoped>
.product-card {
  display: flex;
  flex-direction: column;
  gap: 16px;
  border-radius: 4px;
  transition: transform 0.2s;
}

.product-card:hover {
  transform: translateY(-2px);
}

.product-card.unavailable {
  opacity: 0.7;
}

.product-image {
  height: 200px;
  background: var(--color-background);
  border-radius: 4px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
}

.placeholder-icon {
  opacity: 0.5;
}

.badge-top {
  position: absolute;
  top: 12px;
  left: 12px;
}

.hot-badge {
  display: flex;
  height: 32px;
  padding: 0 8px;
  align-items: center;
  gap: 4px;
  border-radius: 4px;
  border: 1px solid #f2f2f2;
  background: var(--color-white);
  font-size: 14px;
  font-weight: 400;
  color: var(--color-primary);
}

.discount-badge {
  position: absolute;
  bottom: 12px;
  left: 12px;
  padding: 6px 10px;
  border-radius: 4px;
  background: var(--color-brand-primary);
  color: var(--color-white);
  font-size: 14px;
  font-weight: 700;
  line-height: 14px;
}

.product-info {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.product-brand {
  font-size: 14px;
  font-weight: 400;
  line-height: 16px;
  color: var(--color-secondary);
}

.product-name {
  font-size: 14px;
  font-weight: 400;
  line-height: 16px;
  color: var(--color-primary);
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
  transition: color 0.2s;
}

.product-name.hovered {
  color: var(--color-hover-text);
}

.product-card:hover .product-name {
  color: var(--color-hover-text);
}

.product-price {
  display: flex;
  align-items: center;
  gap: 8px;
}

.current-price {
  font-size: 16px;
  font-weight: 700;
  line-height: 14px;
  color: var(--color-primary);
}

.original-price {
  font-size: 12px;
  font-weight: 400;
  line-height: 14px;
  color: var(--color-secondary);
  text-decoration: line-through;
}

.buy-button {
  display: flex;
  padding: 12px 16px;
  justify-content: center;
  align-items: center;
  border-radius: 4px;
  border: 1px solid var(--color-brand-primary);
  background: var(--color-white);
  color: var(--color-brand-primary);
  font-size: 14px;
  font-weight: 700;
  line-height: 14px;
  transition: all 0.2s;
}

.buy-button:hover:not(.unavailable) {
  background: var(--color-brand-primary);
  color: var(--color-white);
}

.buy-button.unavailable {
  border-color: var(--color-secondary);
  color: var(--color-secondary);
  cursor: not-allowed;
}

@media (max-width: 768px) {
  .product-image {
    height: 160px;
  }
}
</style>
