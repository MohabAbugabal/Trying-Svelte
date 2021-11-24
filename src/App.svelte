<script>
	let firstName = "Mohab";
	let lastName = "Abugabal";
	let color = "blue";
	let showText = false;
	let players = [
	{	id: '1',
		name: 'Marco'
	},
	{	id: '2',
		name: 'John'
	},
	{	id: '3',
		name: 'Saka'
	},
	]

	$: name = firstName + " " + lastName;

	const toggle = () => {
		color = color === "blue" ? "red" : "blue";
		showText = !showText;
	};
</script>

<main>
	<h1 style="color: {color}">Hello {name}!</h1>
	{#if showText}
		<p>
			Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to
			learn how to build Svelte apps.
		</p>
		{:else}
		<p>Nothing</p>
	{/if}
	<button on:click={toggle}>Click Me</button>

	{#each players as player (player.id)}
	<h3>{player.id} - {player.name}</h3>
	{/each}
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
