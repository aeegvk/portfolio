<script>
</script>

<svelte:head>
	<title>Jann's Portfolio</title>
	<meta name="description" content="Jann's Portfolio" />
</svelte:head>

<section>
	<h4 class="info">
		Full Stack Software developer with experience in software architecture and design, and a bit on Developer Operations technologies.
	</h4>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	.info {
		width: 13em;
		font-size: 2em;
		font-weight: 200;
		text-align: right;
		vertical-align: bottom;
		position: absolute;
		bottom: 2rem;
		right: 5rem;
	}

	/* On screens that are 600px or less, set the background color to olive */
	@media screen and (max-width: 600px) {
		.info {
			bottom: 0em;
			right: 1em;
			width: 80%;
			font-size: 1.5em;
		}
	}
</style>
