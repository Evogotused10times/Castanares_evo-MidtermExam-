<template>
	<div>
	  <ul v-if="products.length">
		<li v-for="(product, index) in products" :key="index">
		  <div v-if="!editMode || editIndex !== index">
			<h3>{{ product.name }}</h3>
			<p>Price: {{ product.price }}</p>
			<p>{{ product.description }}</p>
			<button @click="editProduct(index)">Edit</button>
		  </div>
		  <div v-else>
			<input v-model="editProductData.name" type="text" />
			<input v-model="editProductData.price" type="number" />
			<textarea v-model="editProductData.description"></textarea>
			<button @click="saveEdit(index)">Save</button>
		  </div>
		</li>
	  </ul>
	  <p v-else>No products available.</p>
	</div>
  </template>
  
  <script>
  export default {
	props: ['products'],
	data() {
	  return {
		editMode: false,
		editIndex: null,
		editProductData: {
		  name: '',
		  price: 0,
		  description: '',
		}
	  };
	},
	methods: {
	  editProduct(index) {
		this.editMode = true;
		this.editIndex = index;
		this.editProductData = { ...this.products[index] };
	  },
	  saveEdit(index) {
		this.$emit('update-product', { index, product: this.editProductData });
		this.editMode = false;
		this.editIndex = null;
	  }
	}
  };
  </script>
  