<script>
	import Header from './Header.svelte';
	import Sidebar from './Sidebar.svelte';
	import './styles.css';
</script>

<div class="app">
	<Header />
	<Sidebar />
	<main>
		<slot />
	</main>
	
</div>

<style>
	.app {
		display: block;
		position: absolute;
		flex-direction: column;
		min-height: 92vh;
		min-width: 92vw;
		height: 92vh;
		width: 92vw;
		height: 92vh;
		border: 0.1em solid var(--color-bg-1);
		margin: 4vh 4vw;
		background-color: #22223B00;
		overflow-y:scroll;
    	overflow-x:hidden;
		box-shadow: 0em 0em 2em 5em #00000055;
	}

	main {
		display: flex;
		flex-direction: column;
		padding: 1rem;
		padding-left: 10rem;
		width: 100%;
		max-width: 64rem;
		margin: 0 0 0 auto;
		box-sizing: border-box;
		overflow: hidden;
		margin-top: 7rem;
	}
</style>
