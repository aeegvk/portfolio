<svelte:head>
	<title>Projects</title>
	<meta name="description" content="Projects" />
</svelte:head>

<section>
	<h3>No projects added yet...</h3>
</section>

<style>
	section {
		width: 13em;
		font-size: 2em;
		font-weight: 100;
		text-align: right;
		vertical-align: bottom;
		position: absolute;
		bottom: 2rem;
		right: 5rem;
	}

	/* On screens that are 600px or less, set the background color to olive */
	@media screen and (max-width: 600px) {
		section {
			bottom: 0em;
			right: 1em;
			width: 80%;
			font-size: 1em;
		}
	}
</style>