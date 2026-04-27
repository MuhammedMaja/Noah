<script>
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<nav>
	<a href="/">Home Page</a>
	<a href="/photoapp">Photo App</a>
	<a href="register"> Register </a>
	<a href="loggin"> Logga in </a>
	<a href="/shoppinglist"> Shopping list </a>
	<a href="/memory"> Memory </a>
	<a href="/test"> Test </a>

</nav>

<style>
	
:global(body), :global(html){
  margin: 0%;
  padding: 0%;
  height: 100vh;
  width: 100vw;
}    

</style>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

{@render children?.()}
