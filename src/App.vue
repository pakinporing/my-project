<template>
  <div id="app">
    <!-- Unordered List -->
    <ul>
      <li v-for="(result, index) in results" :key="index">{{ result }}</li>
    </ul>

    <!-- Table
    <table>
      <tr v-for="(result, index) in results" :key="index">
        <td>{{ result }}</td>
      </tr>
    </table> -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: {
        products: [
          {
            variants: ['souffle', 'cake', 'ice-cream']
          },
          {
            variants: ['cherry', 'choco']
          },
          {
            variants: ['XL']
          }
        ]
      },
      results: []
    };
  },
  mounted() {
    this.products.products[1].variants.forEach((item2) => {
      this.products.products[0].variants.forEach((item1) => {
        this.products.products[2].variants.forEach((item3) => {
          this.results.push(`${item1} ${item2} ${item3}`);
        });
      });
    });
  }
};
</script>
