<template>
	<article>
		<h1>{{suit.title}}</h1>
			<p>{{suit.body}}</p>
			<a v-bind:href="suit.link" target="_blank">Armour Details</a>
			<img :src="require(`../assets/suits/${suit.image}`)" id="suit" height="95" width="42"/>
	</article>
</template>

<script>
	export default{
		props: ["suit"]
	};
</script>

<style>
	@import '../assets/css/suit.css';
</style>
