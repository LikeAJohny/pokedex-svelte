<script>
	import { pokemon } from '../stores/poke.store';
</script>

<h1 class="text-4xl text-center my-8 uppercase">Pokedex</h1>

{#each $pokemon as pokeman}
  <p>{pokeman.name}</p>
{/each}
