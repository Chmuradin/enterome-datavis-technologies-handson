<script>
	let clicked = false;
</script>

<div>
	<button class="btn btn-primary" on:click={() => (clicked = true)}>
		click here
	</button>
	<!--  -->
</div>

<ul>
{#if clicked == true}
	<h2>You have clicked the button!</h2>
{:else}
	<h2>You have to click the button!</h2>
{/if}
</ul>