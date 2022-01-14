<script>
	import { pokemon } from '../stores/poke.store';
</script>

{#each $pokemon as pokeman}
  <p>{pokeman.name}</p>
{/each}