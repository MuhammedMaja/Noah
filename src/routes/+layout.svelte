<script>
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();

	let {base} = '$app/paths';
</script>

<nav>
	<a href="{base}/">Home Page</a>
	<a href="{base}/photoapp">Photo App</a>
	<a href="{base}/register"> Register </a>
	<a href="{base}/loggin"> Logga in </a>
	<a href="{base}/shoppinglist"> Shopping list </a>
	<a href="{base}/memory"> Memory </a>
	<a href="{base}/test"> Test </a>

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
