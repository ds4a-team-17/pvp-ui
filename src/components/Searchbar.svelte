<script>
  export let predictions;
  var loading = false;

  const predictVolume = async () => {
    loading = true;
    var description = document.getElementById("description-input").value;
    const response = await fetch(
      "https://ds4a-pvp-backend.herokuapp.com/predict?description=" +
        description
    );
    const data = await response.json();
    loading = false;
    predictions = [
      {
        description: description,
        value: data.predictionCubicWeight,
        unit: data.cubicWeightUnit,
        probabilities: data.probabilities,
      },
      ...predictions,
    ];
    predictions.splice(5);
  };

  const onKeyPress = (e) => {
    if (e.charCode === 13) predictVolume();
  };
</script>

<div class="container search-bar">
  <div class="row">
    <div class="col s9">
      <input
        type="text"
        id="description-input"
        placeholder="Tenis mizuno"
        on:keypress={onKeyPress}
      />
    </div>
    <div class="col s3">
      <button
        class="btn waves-effect waves-light"
        type="submit"
        name="action"
        on:click={() => predictVolume()}
      >
        <i class="tiny material-icons left">search</i>
        Search
      </button>
    </div>
  </div>
</div>
{#if loading}
  <div class="row">
    <div class="col s8 offset-s2">
      <div class="progress">
        <div class="indeterminate" />
      </div>
    </div>
  </div>
{/if}

<style>
  .search-bar {
    margin-top: 1em;
  }
</style>
