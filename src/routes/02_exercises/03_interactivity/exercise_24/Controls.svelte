<script>
  // Properties
  export let data = [];
  export let year = 0; //1800
  export let cont_dropdown = "all";  
  const continents = ["europe", "asia", "americas", "africa"];
  let timer = false;
  let clicked = false; 
  function increment() { 
    year == 200 ? year = 0 : year += 1
  }
  function start() {
    if (timer == false) {
      timer = setInterval(increment, 50); 
      clicked = true;
    } else {
      clearInterval(timer); 
      timer = false;
      clicked = false; 
    }
  } 
  function reset() {
    clearInterval(timer);
    timer = false;
    year = 0;
    clicked = false; 
  } 
</script>

<div class="row">
  <div>
    {#if clicked == false}
      <button class="btn btn-success" on:click={start}>Start</button>
    {:else}
      <button class="btn btn-danger" on:click={start}>Stop</button>
    {/if}
      <button class="btn btn-secondary" on:click={reset}>Reset</button>
  </div>
  <div> 
    <select class="btn btn-primary dropdown-toggle" data-toggle="dropdown" bind:value={cont_dropdown}>
      <option value="all">All continents</option>
      <option value="europe">Europe</option>
      <option value="asia">Asia</option>
      <option value="americas">Americas</option>
      <option value="africa">Africa</option>
    </select> 
  </div>
  <div>
    <label for="slider">Year: {1800 + year}</label>
    <input type="range" class="form-range" min="0" max="200" bind:value={year} id="slider">
  </div> 
  

</div>