<script setup lang="ts">
import CartProduct from './CartProduct.vue'
import type { ProductCartInterface } from '@/interfaces'
defineProps<{
  cart: ProductCartInterface[]
}>()
const emit = defineEmits<{
  (e: 'removeProductFromCart', productId: number): void;
}>();
</script>

<template>
  <div class="d-flex flex-column">
    <CartProduct v-for="product of cart" :key="product.id" :product="product"
     @remove-product-from-cart="emit('removeProductFromCart', $event)"
    />
  </div>
</template>

<style scoped lang="scss"></style>
