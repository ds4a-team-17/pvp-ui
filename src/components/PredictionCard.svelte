<script>
  export let prediction;
</script>

<div class="row">
  <div class="col s8 offset-s2">
    <div class="card blue-grey darken-1">
      <div class="card-content white-text">
        <span class="card-title activator"
          >{prediction.description}<i class="material-icons right">more_vert</i></span
        >
        <p>
          cubic weight: {prediction.cubicWeightValue}{prediction.cubicWeightUnit}
        </p>
        <p>
          volume: {prediction.volumeValue.toFixed(0)}{prediction.volumeUnit}
        </p>
      </div>
      <div class="card-reveal blue-grey darken-1 white-text">
        {prediction.description}
        <span class="card-title"><i class="material-icons right">close</i></span
        >
        <p>
          {#each Object.entries(prediction.probabilities) as [value, probability]}
            {value}{prediction.cubicWeightUnit} ({(probability * 100).toFixed(2)}%)&nbsp;
          {/each}
        </p>
      </div>
    </div>
  </div>
</div>
