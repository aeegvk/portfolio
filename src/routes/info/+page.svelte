<script>
	import github from '$lib/images/github.svg';
</script>

<svelte:head>
	<title>Info</title>
	<meta name="description" content="Info" />
</svelte:head>

<section>
	<div>
		<a href="https://github.com/aeegvk">
			<img src={github} alt="GitHub" />
		</a>
	</div>
</section>

<style>
	section {
		vertical-align: bottom;
		width: 3em;
		text-align: right;
		margin: 0 0 0 auto;
		position: fixed;
		bottom: 4em;
		right: 5em;
	}

	img {
		vertical-align: bottom;
		width: 3em;
		filter: invert(100%);
	}
</style>