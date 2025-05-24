<template>
  <v-container>
    <h1>Products List</h1>
    <v-data-table
		:headers="headers"
		:items="products"
		:items-per-page="itemsPerPage"
		:page="page"
		:items-per-page-options="itemsPerPageOptions"
		items-per-page-text="Products per page:"
		items-per-page-all-text="Show all products"
	  ></v-data-table>
  </v-container>
</template>

<script setup>
import { ref } from 'vue';

// Table configuration
const itemsPerPage = ref(5);
const page = ref(1);
const itemsPerPageOptions = ref([
	{ value: 5, title: '5 items' },
	{ value: 10, title: '10 items' },
	{ value: 15, title: '15 items' },
	{ value: -1, title: 'All' }
]);

// Table headers
const headers = ref([
	{ title: 'Product ID', key: 'id', align: 'start', sortable: true },
	{ title: 'Product Name', key: 'name', align: 'start', sortable: true },
	{ title: 'Category', key: 'category', align: 'start', sortable: true },
	{ title: 'Price ($)', key: 'price', align: 'end', sortable: true },
	{ title: 'Stock', key: 'stock', align: 'end', sortable: true }
]);

// Sample data
const products = ref([
	{
		id: 1,
		name: 'Laptop Pro X1',
		category: 'Electronics',
		price: 1299.99,
		stock: 45
	},
	{
		id: 2,
		name: 'Smartphone Galaxy',
		category: 'Electronics',
		price: 899.99,
		stock: 120
	},
	{
		id: 3,
		name: 'Coffee Maker Deluxe',
		category: 'Kitchen',
		price: 89.99,
		stock: 30
	},
	{
		id: 4,
		name: 'Ergonomic Office Chair',
		category: 'Furniture',
		price: 199.99,
		stock: 15
	},
	{
		id: 5,
		name: 'Wireless Headphones',
		category: 'Electronics',
		price: 149.99,
		stock: 75
	},
	{
		id: 6,
		name: 'Fitness Tracker',
		category: 'Wearables',
		price: 79.99,
		stock: 60
	},
	{
		id: 7,
		name: 'Blender Pro',
		category: 'Kitchen',
		price: 69.99,
		stock: 25
	},
	{
		id: 8,
		name: 'Smart Watch',
		category: 'Wearables',
		price: 249.99,
		stock: 40
	},
	{
		id: 9,
		name: 'Wireless Mouse',
		category: 'Computer Accessories',
		price: 29.99,
		stock: 100
	},
	{
		id: 10,
		name: 'External SSD 1TB',
		category: 'Storage',
		price: 129.99,
		stock: 35
	},
	{
		id: 11,
		name: 'Gaming Keyboard',
		category: 'Computer Accessories',
		price: 89.99,
		stock: 50
	},
	{
		id: 12,
		name: 'Desk Lamp',
		category: 'Lighting',
		price: 39.99,
		stock: 80
	}
]);
</script>

<style scoped>
.v-data-table {
	margin-top: 20px;
}
</style>