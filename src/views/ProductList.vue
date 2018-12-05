<template>
  <ul class="product-list">
    <li v-for="product in products" v-bind:key="product.id">
      <ProductComponent v-bind:product="product"/>
    </li>
  </ul>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import ProductComponent from '@/components/ProductComponent.vue'; // @ is an alias to /src

const products = [
  {
    id: '1',
    title: 'Hat',
    description: 'Nice hat',
  },
  {
    id: '2',
    title: 'Scarf',
    description: 'Red scarf',
  },
];

@Component({
  components: {
    ProductComponent,
  },
})
export default class ProductList extends Vue {
  private data() {
    return { products };
  }
}
</script>
