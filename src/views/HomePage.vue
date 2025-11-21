<template>
  <div class="home-page">
    <FilterSidebar />

    <main class="product-grid-container">
      <div class="product-grid">
        <ProductCard
          v-for="(product, index) in products"
          :key="index"
          :brand="product.brand"
          :name="product.name"
          :current-price="product.currentPrice"
          :original-price="product.originalPrice"
          :discount="product.discount"
          :available="product.available"
        />
      </div>
    </main>
  </div>
</template>

<script setup lang="ts">
import FilterSidebar from '@/components/FilterSidebar.vue'
import ProductCard from '@/components/ProductCard.vue'

const products = [
  {
    brand: 'Бренд',
    name: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    currentPrice: '5 990',
    originalPrice: '5 990',
    discount: 25,
    available: true
  },
  {
    brand: 'Бренд',
    name: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    currentPrice: '5 990',
    originalPrice: '5 990',
    discount: 25,
    available: true
  },
  {
    brand: 'Бренд',
    name: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    currentPrice: '5 990',
    originalPrice: '5 990',
    discount: 25,
    available: false
  },
  {
    brand: 'Бренд',
    name: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    currentPrice: '5 990',
    originalPrice: '5 990',
    discount: 25,
    available: true
  },
  {
    brand: 'Бренд',
    name: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    currentPrice: '5 990',
    originalPrice: '5 990',
    discount: 25,
    available: true
  },
  {
    brand: 'Бренд',
    name: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    currentPrice: '5 990',
    originalPrice: '5 990',
    discount: 25,
    available: true
  },
  {
    brand: 'Бренд',
    name: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    currentPrice: '5 990',
    originalPrice: '5 990',
    discount: 25,
    available: true
  },
  {
    brand: 'Бренд',
    name: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    currentPrice: '5 990',
    originalPrice: '5 990',
    discount: 25,
    available: true
  },
  {
    brand: 'Бренд',
    name: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    currentPrice: '5 990',
    originalPrice: '5 990',
    discount: 25,
    available: true
  },
  {
    brand: 'Бренд',
    name: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    currentPrice: '5 990',
    originalPrice: '5 990',
    discount: 25,
    available: true
  },
  {
    brand: 'Бренд',
    name: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    currentPrice: '5 990',
    originalPrice: '5 990',
    discount: 25,
    available: true
  },
  {
    brand: 'Бренд',
    name: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    currentPrice: '5 990',
    originalPrice: '5 990',
    discount: 25,
    available: true
  }
]
</script>

<style scoped>
.home-page {
  display: flex;
  gap: 36px;
  padding: 0 100px 36px;
  max-width: 1440px;
  margin: 0 auto;
  width: 100%;
}

.product-grid-container {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.product-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 24px;
  align-items: start;
}

@media (max-width: 1200px) {
  .home-page {
    padding: 0 40px 36px;
  }
  
  .product-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media (max-width: 1024px) {
  .product-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .home-page {
    padding: 0 20px 24px;
  }
  
  .product-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 16px;
  }
}

@media (max-width: 480px) {
  .product-grid {
    grid-template-columns: 1fr;
  }
}
</style>
