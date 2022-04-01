<template>
  Cart

  <div class="grid grid-cols-4 gap-4">
    <div
      v-for="product in products"
      :key="product.id"
      class="border rounded-lg"
    >
      <img :src="product.image" class="w-full rounded-t-lg" />
      <div class="p-4">
        <div>{{ product.name }}</div>
        <div>{{ product.price }}€</div>
        <button
          @click="addToCart(product)"
          class="bg-teal-700 text-white rounded px-3 py-2 w-full"
        >
          Add to cart
        </button>
      </div>
    </div>
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
    products() {
      return this.cartStore.cartProducts;
    },
  },
  methods: {
    addToCart(product) {
      this.cartStore.cartProducts.push(product);
    },
  },
};
</script>
