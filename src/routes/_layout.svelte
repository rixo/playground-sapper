<script>
	import Nav from '../components/Nav.svelte';

	export let segment;
</script>

<style lang="scss" global>
	// NOTE This is not where I would have wanted to put my global style, but I
	// failed to configure rollup-plugin-postcss in a compatible way with Svelte.
	//
	// WARNING The `global` attribute above is needed here, otherwise the imported
	// rules will still be scoped by Svelte. As a consequence, that also means
	// that _any other rules_ in this component (like the `main` bellow) will also
	// be global. Might be worth it to extract all this into its own Svelte
	// component with the sole responsability of managing global styles.
	//
	@import '../style/shared.scss';

	main {
		position: relative;
		max-width: 56em;
		background-color: white;
		padding: 2em;
		margin: 0 auto;
		box-sizing: border-box;
	}
</style>

<Nav {segment}/>

<main>
	<slot></slot>
</main>
