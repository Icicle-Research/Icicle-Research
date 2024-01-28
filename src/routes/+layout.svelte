<script lang="ts">
	import Header from '$lib/components/Header.svelte';
    import Navbar from '$lib/components/Navbar.svelte';
    import Footer from '$lib/components/Footer.svelte';
    import { onMount } from 'svelte';
    onMount(() => {
        console.log('mounted');
    });
	import '../app.css';
</script>

<Header />

<main class="">
    <Navbar />
	<slot />
    <Footer/>
</main>

<footer>
</footer>

<style>
	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		/* padding: 1rem; */
		/* width: 100%; */
		/* max-width: 1440px; */
		/* margin: 0 auto; */
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 40px;
	}



	@media (min-width: 480px) {
		footer {
			padding: 40px 0;
		}
	}
</style>