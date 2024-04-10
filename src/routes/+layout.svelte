<script lang="ts">
	import Header from '../lib/Header.svelte';
	import HamburgerMenu from '../lib/HamburgerMenu.svelte';
	import MouseStalker from '../lib/MouseStalker.svelte';
	import 'normalize.css';
	import '../styles/styles.scss';
</script>

<div class="app">
	<Header />

	<MouseStalker />
	<main>
		<slot />
		<HamburgerMenu />
	</main>

</div>

<style lang="scss">
	.app {

		min-height: 100vh;

	}

	main {

		box-sizing: border-box;
		position: relative;
	}

	@media (min-width: 480px) {
		footer {
			padding: 12px 0;
		}
	}
</style>
