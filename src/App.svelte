<script>
	import Quiz from "./components/Quiz.svelte";
	import Setup from "./components/Setup.svelte";
	import Results from "./components/Results.svelte";
	import { hasQuizBegun, isQuizDone } from "./data/store.js";
</script>

<style>
	:global(body) {
		background: #efefef;
		color: #222;
	}
	:global(button) {
		box-sizing: border-box;
		margin: 1em 0;
		background: transparent;
		color: #222;
		cursor: pointer;
		border: 2px solid #222;
		padding: 1em 0;
		font-size: 0.9em;
		transition: 0.2s all;
		width: 100%;
	}
	:global(button:hover, button:focus) {
		background: #222;
		color: #efefef;
		transform: scale(1.05);
	}
	:global(button:active) {
		background: #222;
		color: #efefef;
		transform: scale(1);
	}
	main {
		font-size: 30px;
		margin: 0 auto;
		max-width: 600px;
		text-align: center;
	}
	@media only screen and (max-width: 600px) {
		main {
			font-size: 24px;
		}
	}
</style>

<main>
	{#if $hasQuizBegun}
		<Quiz />
	{:else if $isQuizDone}
		<Results />
	{:else}
		<Setup />
	{/if}
</main>
