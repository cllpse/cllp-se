<template>
	<div id="app">
		<p>C</p>
		<p class="vowel">O</p>
		<p>L</p>
		<p>L</p>
		<p class="vowel">A</p>
		<p>P</p>
		<p>S</p>
		<p>E</p>
	</div>
</template>

<script lang="ts">
	import { Vue } from "vue-property-decorator";

	export default class App extends Vue {}
</script>

<style lang="postcss">
	@keyframes fade-in
	{
		100%
		{
			opacity: 1;
		}
	}

	@keyframes collapse-vowels
	{
		50%
		{
			opacity: 0;
		}

		100%
		{
			width: 0;
			opacity: 0;
		}
	}

	@keyframes collapse-all
	{
		100%
		{
			width: 5.33vw;
		}
	}

	html,
	body
	{
		width: 100%;
		height: 100%;
	}

	body
	{
		user-select: none;
		display: flex;
		justify-content: center;
		align-items: center;
		margin: 0;
		padding: 0;
		background-color: black;
		color: white;
		font-family: "Share Tech Mono";
		font-weight: 700;
	}

	#app
	{
		animation: 0.15s fade-in ease-in forwards;
		opacity: 0;
	}

	p
	{
		will-change: width, opacity;
		display: inline-block;
		width: 9vw;
		overflow: hidden;
		animation: 5s collapse-all ease-in-out forwards 0.15s;
		margin: 0;
		line-height: 9vw;
		text-align: center;
		font-size: 9vw;
	}

	p.vowel
	{
		animation: 5s collapse-vowels ease-in-out forwards 0.15s;
	}
</style>
