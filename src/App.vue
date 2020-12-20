<template>
	<div>
		<h1>Hello World</h1>
		<p> {{ msg }} </p>
	</div>
</template>

<script>
export default {
	data: function() {
		return {
			msg: "Welcome to your new vue app"
		}
	}
}
</script>

<style>
	* {
		background-color: #dedede;
	}

	div {
		text-align: center;
	}
</style>