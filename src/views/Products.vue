
<template>
	<div>
	<h1 >Product Management</h1>
	  <ProductForm @add-product="addProduct" />
	  <ProductList :products="products" @update-product="updateProduct" />
	</div>
  </template>

  <script>
  import ProductForm from '@/components/ProductForm.vue';
  import ProductList from '@/components/ProductList.vue';
  
  export default {
	components: {
	  ProductForm,
	  ProductList
	},
	data() {
	  return {
		products: []
	  };
	},
	methods: {
	  addProduct(product) {
		this.products.push(product);
	  },
	  updateProduct({ index, product }) {
		this.products.splice(index, 1, product);
	  }
	}
  };
  </script>
<style scoped>
div {
	margin-top: 20px;
	padding: 10px;
	color: aqua;
	justify-content: center;
	text-align: center;
	background-color:darkolivegreen;
	border-radius: 8px;
}
h1 {
	text-align: center;
}

</style>