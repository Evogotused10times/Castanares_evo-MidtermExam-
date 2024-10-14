<template>
	<form @submit.prevent="submitForm">
	  <div>
		<label for="name">Product Name</label>
		<input v-model="product.name" type="text" id="name" required />
	  </div>
  
	  <div>
		<label for="price">Price</label>
		<input v-model="product.price" type="number" id="price" required />
	  </div>
  
	  <div>
		<label for="description">Description</label>
		<textarea v-model="product.description" id="description"></textarea>
	  </div>
  
	  <button type="submit">Add Product</button>
	</form>
  </template>
  
  <script>
  export default {
	data() {
	  return {
		product: {
		  name: '',
		  price: 0,
		  description: '',
		}
	  };
	},
	methods: {
	  submitForm() {
		this.$emit('add-product', { ...this.product });
		this.product.name = '';
		this.product.price = 0;
		this.product.description = '';
	  }
	}
  };
  </script>
  