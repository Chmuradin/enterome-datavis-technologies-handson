<script>
    let count = 0;
function handle(event) {
    count += 1;
}
function reset(event) {
    count = 0;
}
</script>

<button class="btn btn-info" on:click={handle}> Count: {count} </button>
<button class="btn btn-warning" on:click={reset}> Reset </button>