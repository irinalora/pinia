<template>
  <div class="bg-gray-100 shadow flex justify-between items-center px-4">
    <RouterLink to="/" class="py-4">PiniaStore</RouterLink>
    <RouterLink to="/cart">{{ numItems }}</RouterLink>
  </div>
</template>

<script>
import { useCart } from "../stores/cart";

export default {
  setup() {
    const cartStore = useCart();

    return { cartStore };
  },
  computed: {
    numItems() {
      return this.cartStore.cartProducts.length;
    },
  },
};
</script>
