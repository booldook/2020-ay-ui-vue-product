<template>
	<form v-on:submit.prevent="onSubmit" id="search-form" class="position-relative">
		<input v-model="query" type="text" id="query" class="form-control" placeholder="검색어를 입력하세요." autofocus>
		<i v-on:click="onReset" v-show="query.length" id="btReset" class="fa fa-times-circle"></i>
	</form>
</template>

<script>
export default {
	name: "search-bar",
	data() {
		return {
			query: ""
		}
	},
	methods: {
		onSubmit() {

		},
		onReset() {
			this.query = '';
		}
	}
}
</script>

<style lang="less">
#btReset {position: absolute; top: 12px; right: 12px; cursor: pointer;}
</style>