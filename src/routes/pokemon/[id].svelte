<script context="module">
	import { getPokemonById } from '../../pokestore';

	export async function load(ctx) {
		let id = ctx.params.id;
		const pokemon = await getPokemonById(id);
    console.log(pokemon);

		return { props: { pokemon } };
	}
</script>

<script>
	export let pokemon;

	const type = pokemon.types[0].type.name;
</script>

<svelte:head>
	<title>Pokedex - {pokemon.name}</title>
</svelte:head>

<div class="flex flex-col items-center">
	<h1 class="text-4xl text-center my-8 uppercase">{pokemon.name}</h1>
	<p>
		Type: <strong>{type}</strong> | Height: <strong>{pokemon.height}</strong>
		| Weight: <strong>{pokemon.weight}</strong>
	</p>
	<img class="w-40 h-40" src={pokemon.sprites['front_default']} alt={pokemon.name} />
</div>
