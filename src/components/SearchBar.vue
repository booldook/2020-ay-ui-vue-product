<template>
	<form v-on:submit.prevent="onSubmit" id="search-form" class="position-relative">
		<input v-model="inputQuery" type="text" id="query" class="form-control" placeholder="검색어를 입력하세요." autofocus>
		<i v-on:click="onReset" v-show="inputQuery.length" id="btReset" class="fa fa-times-circle"></i>
	</form>
</template>

<script>
export default {
	name: "search-bar",
	props: ['query'],
	data() {
		return {
			inputQuery: ""
		}
	},
	methods: {
		onSubmit() {
			this.$emit('@submit', this.inputQuery);
		},
		onReset() {
			this.inputQuery = '';
			this.$emit('@reset', this.inputQuery);
		}
	}
}
</script>

<style lang="less">
#btReset {position: absolute; top: 12px; right: 12px; cursor: pointer;}
</style>