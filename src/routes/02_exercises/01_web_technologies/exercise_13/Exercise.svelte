<script>
	const videos = [
		{ url: 'https://www.youtube.com/watch?v=S4bn6gg-BmE', name: 'Messi' },
		{ url: 'https://www.youtube.com/watch?v=MD6WXsjdcsY', name: 'Ronaldo' },
		{ url: 'https://www.youtube.com/watch?v=yTGr45ZQRdA', name: 'Neymar' }
	];
</script>
<div>
	<h4>Famous soccer players:</h4>
	<ul>
		{#each videos as v}
			<li>{v.name} <a href={v.url}> {v.url}</a> </li>
		{/each}
	</ul>
</div>