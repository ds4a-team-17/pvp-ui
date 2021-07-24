<script>
  import Searchbar from "../components/Searchbar.svelte";
  import PredictionCard from "../components/PredictionCard.svelte";
  var predictions = [];
</script>

<Searchbar bind:predictions />

{#each predictions as { description, value, unit, probabilities }}
  <PredictionCard {description} {value} {unit} {probabilities} />
{/each}
