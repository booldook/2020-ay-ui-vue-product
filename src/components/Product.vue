<template>
	<div class="prd-wrap">
		<div class="prd" v-for="v in prds" v-bind:key="v.id">
			<img v-bind:src="`/img/${v.src}`" alt="상품" class="w-100">
			<div class="title">{{v.title}}</div>
			<div class="price">{{v.price}}</div>
		</div>
	</div>
</template>

<script>
import axios from 'axios';

export default {
	name: "Product",
	props: ['query'],
	data() {
		return {
			prds: []
		}
	},
	watch: {
		query: async function(newValue, oldValue) {
			var res = await axios.get("/json/products.json");
			this.prds = res.data.products;
		}
	},
	created() {
		
	}
}
</script>

<style lang="less">
.prd-wrap {
	display: flex;
	flex-wrap: wrap;
	.prd {
		flex: 23% 0 0;
		margin: 1%;
		border: 1px solid #ccc;
		padding: 12px;
		.title {
			font-size: 1.5rem;
		}
		.price {
			font-size: 1.25rem;
			color: #999;
		}
	}
}
</style>