<script>
    import Searchbar from '../components/Searchbar.svelte';
    import PredictionCard from '../components/PredictionCard.svelte';
    var predictions = [];
</script>

<Searchbar bind:predictions={predictions} />


{#each predictions as {description, value, unit, probabilities}}
    <PredictionCard description={description} value={value} unit={unit} probabilities={probabilities} />
{/each}

