<template>
	<div class="prd-wrap">
		<div class="prd">
			<img src="../assets/img/p1.jpg" alt="상품" class="w-100">
			<div class="title">PRODUCT</div>
			<div class="price">$25.00</div>
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