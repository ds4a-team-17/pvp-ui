<script>
  export let value;
  export let description;
  export let unit;
  export let probabilities;
</script>

<div class="row">
  <div class="col s8 offset-s2">
    <div class="card blue-grey darken-1">
      <div class="card-content white-text">
        <span class="card-title activator"
          >{description}<i class="material-icons right">more_vert</i></span
        >
        <p>{value}{unit}</p>
      </div>
      <div class="card-reveal blue-grey darken-1 white-text">
        {description}
        <span class="card-title"><i class="material-icons right">close</i></span
        >
        <p>
          {#each Object.entries(probabilities) as [value, probability]}
            {value}{unit} ({(probability * 100).toFixed(2)}%)&nbsp;
          {/each}
        </p>
      </div>
    </div>
  </div>
</div>
